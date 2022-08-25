# How_to_get_user_permission Kotlin

Hi Coders! 🖐

I will explain that how to get all kind of user permissions. It will better to make an example.

🚀Here we go wtih location permission example:

1- Open your manifest file and add uses permission as below ;

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    
<img width="960" alt="1" src="https://user-images.githubusercontent.com/88722745/186642177-60b9722a-d9fc-4a07-ba0b-2e5d63335f0b.png">

2-Open Your activity where you will ask permission and add below code ;

if (ContextCompat.checkSelfPermission(this,
                Manifest.permission.ACCESS_FINE_LOCATION) !==
            PackageManager.PERMISSION_GRANTED) {
            if (ActivityCompat.shouldShowRequestPermissionRationale(this,
                    Manifest.permission.ACCESS_FINE_LOCATION)) {
                ActivityCompat.requestPermissions(this,
                    arrayOf(Manifest.permission.ACCESS_FINE_LOCATION), 1)
            } else {
                ActivityCompat.requestPermissions(this,
                    arrayOf(Manifest.permission.ACCESS_FINE_LOCATION), 1)
            }
        }
    }
    override fun onRequestPermissionsResult(requestCode: Int, permissions: Array<String>,
                                            grantResults: IntArray) {
        super.onRequestPermissionsResult(requestCode, permissions, grantResults)
        when (requestCode) {
            1 -> {
                if (grantResults.isNotEmpty() && grantResults[0] ==
                    PackageManager.PERMISSION_GRANTED) {
                    if ((ContextCompat.checkSelfPermission(this,
                            Manifest.permission.ACCESS_FINE_LOCATION) ===
                                PackageManager.PERMISSION_GRANTED)) {
                        Toast.makeText(this, "Location permissiom succes", Toast.LENGTH_SHORT).show()
                    }
                } else {
                    Toast.makeText(this, "Location permission denied", Toast.LENGTH_SHORT).show()
                }
                return
            }
        }
     
     <img width="960" alt="2" src="https://user-images.githubusercontent.com/88722745/186643230-896f331e-28f0-4029-b2a0-5823f9a1e6ae.png">

     
     That' ALL 😊
        

