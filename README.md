# EaseOfLiveData

First you have to enable DataBinding for Simple use of View Access
Add below line in Module Level Gradle File

dataBinding {
        enabled = true
    }
    
buildTypes.each {
        it.buildConfigField 'double', 'ANS', cAnswer
        it.buildConfigField 'String', 'BASE_URL', BASE_URL
        it.buildConfigField 'String', 'UPLOAD_URL', UPLoad_URL
        it.buildConfigField 'String', 'BASE_SERVICE', BASE_SERVICES
    }
    
Also add some required Dependencies to use LiveData, Observabale Pattern and RxJava

Dependency List & Versions :
PROJECT LEVEL : 
ext{
        materialVer = '1.3.0-rc01'
        archLifeCycleVer = '2.1.1'
        gsonVer = '2.8.5'
        retroVer = '2.5.0'
        retInterVer = '4.2.2'
        rxJavaAdapterVersion = '2.3.0'
        rxandroidVer = '2.1.1'
        rxjavaVer = '2.2.15'
        rxbindingVer = '3.0.0-alpha2'
        glideVer = '4.8.0'
    }
        
MODUEL LEVEL :
    /*Material Library */
    implementation "com.google.android.material:material:$materialVer"

    // Lifecycle library for viewmodel
    implementation "android.arch.lifecycle:viewmodel:$archLifeCycleVer"

    // for LiveData
    implementation "android.arch.lifecycle:extensions:$archLifeCycleVer"

    // retorfit2
    implementation "com.google.code.gson:gson:$gsonVer"
    implementation("com.squareup.retrofit2:retrofit:$retroVer") {
        exclude module: 'okhttp'
    }
    implementation "com.squareup.retrofit2:adapter-rxjava2:$rxJavaAdapterVersion"
    implementation "com.squareup.retrofit2:converter-gson:$retroVer"
    implementation "com.squareup.okhttp3:logging-interceptor:$retInterVer"

    //RxJava
    implementation "io.reactivex.rxjava2:rxandroid:$rxandroidVer"
    implementation "io.reactivex.rxjava2:rxjava:$rxjavaVer"
    implementation "com.jakewharton.rxbinding3:rxbinding:$rxbindingVer"
    
