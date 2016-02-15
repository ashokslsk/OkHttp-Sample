# OkHttpNetworkRequest
Sample OkHttp GET Network request 

#Step 1: Add the following dependency
```sh
dependencies {
    compile 'com.squareup.okhttp3:okhttp:3.1.2'
}
```


#Step 2: Add internet permission in your manifest
```sh   
 <uses-permission android:name="android.permission.INTERNET"/>

```

#Step 3: Enjoy the asynctask code with OkHttp 
```sh

new AsyncTask<Void,Void,String>(){

            @Override
            protected String doInBackground(Void... params) {

                OkHttpClient client = new OkHttpClient();
                Request request = new Request.Builder()
                        .url("https://api.github.com/users/your_username")
                        .build();

                try {
                    Response response = client.newCall(request).execute();
                    Log.d(TAG, "doInBackground() called with: " + "params = [" + response.body().string() + "]");
                    return response.body().string();
                } catch (IOException e) {
                    e.printStackTrace();
                }

                return null;
            }
        }.execute();
```


Finally your done now.

- Execute the code with your api key and you are done simple as it is 

* [For more codes, funs and for queries be in touch with @ashokslsk ](https://github.com/ashokslsk)

## License

```
    Copyright 2016 Ashokslsk.

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
```

