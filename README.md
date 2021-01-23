

      private void imageOnClickDialog(String imageUrl) {
        Dialog alertDialog = new Dialog(EventPastAndFutureDetailsViewActivity.this);
        alertDialog.setCancelable(true);
        alertDialog.getWindow().getDecorView().setBackgroundResource(android.R.color.transparent);
        alertDialog.requestWindowFeature(Window.FEATURE_NO_TITLE);
        alertDialog.getWindow().getAttributes().windowAnimations = R.style.animationDialog;
        WindowManager.LayoutParams lp = new WindowManager.LayoutParams();
        lp.copyFrom(alertDialog.getWindow().getAttributes());
        lp.width = WindowManager.LayoutParams.MATCH_PARENT;
        lp.height = WindowManager.LayoutParams.MATCH_PARENT;
        ImageView showImage = new ImageView(EventPastAndFutureDetailsViewActivity.this);
        showImage.setLayoutParams(new ViewGroup.LayoutParams(ViewGroup.LayoutParams.MATCH_PARENT, ViewGroup.LayoutParams.MATCH_PARENT));
        alertDialog.setContentView(showImage);
        alertDialog.getWindow().setAttributes(lp);
        Glide.with(showImage.getContext()).setDefaultRequestOptions(new RequestOptions().placeholder(R.drawable.image_loading)).asBitmap().load(imageUrl).error(R.drawable.ic_training).into(showImage);
        alertDialog.show();
        
        showImage.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                alertDialog.dismiss();
            }
        });
    }
    
    //Style file
     <style name="animationDialog" parent="android:Animation">
        <item name="android:windowEnterAnimation">@anim/animation_on</item>
        <item name="android:windowExitAnimation">@anim/animation_off</item>
    </style>
    
    //animation_on
    <scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="300"
    android:fromXScale="0.0"

    android:fromYScale="0.0"
    android:pivotX="0%"

    android:pivotY="50%"
    android:startOffset="100"

    android:toXScale="1.0"
    android:toYScale="1.0" />
    
     //animation_off
     <scale xmlns:android="http://schemas.android.com/apk/res/android"
    android:duration="300"
    android:fromXScale="1.0"

    android:fromYScale="1.0"
    android:pivotX="0%"

    android:pivotY="50%"
    android:startOffset="100"

    android:toXScale="0.0"
    android:toYScale="0.0" />
    
    
