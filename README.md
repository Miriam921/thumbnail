# thumbnail
Android Studio-thumbnail(first time try)
package com.example.thumbnail;

import android.graphics.Bitmap;
import android.graphics.BitmapFactory;
import android.media.ThumbnailUtils;
import android.os.Bundle;
import android.support.v7.app.AppCompatActivity;
import android.widget.ImageView;

public class ThumbnailActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_thumbnail);
        BitmapFactory.Options options = new BitmapFactory.Options();
        options.inSampleSize = 4;
        ImageView image = (ImageView) findViewById(R.id.image);
        Bitmap bitmap = BitmapFactory.decodeResource(getResources(), R.drawable.i1);
        bitmap = ThumbnailUtils.extractThumbnail(bitmap,100, 100);
        image.setImageBitmap(bitmap);
    }
}
