package(default_visibility = ["//visibility:public"])

android_library(
    name = "firestore_config_manager_impl",
    srcs = ["FirestoreInitializer.java"],
    deps = ["@com_google_firebase_firebase_common_11_8_0//aar"],
)

android_library(
    name = "firestore",
    exports = [
        "//third_party/maven/com/squareup/okhttp",
        "//third_party/maven/com/squareup/okio",
        "@com_android_support_support_annotations_27_0_2//jar",
        "@com_android_support_support_compat_27_0_2//aar",
        "@com_android_support_support_core_ui_27_0_2//aar",
        "@com_android_support_support_core_utils_27_0_2//aar",
        "@com_android_support_support_fragment_27_0_2//aar",
        "@com_android_support_support_media_compat_27_0_2//aar",
        "@com_android_support_support_v4_27_0_2//aar",
        "@com_google_android_gms_play_services_basement_11_8_0//aar",
        "@com_google_android_gms_play_services_basement_license_11_8_0//aar",
        "@com_google_android_gms_play_services_tasks_11_8_0//aar",
        "@com_google_android_gms_play_services_tasks_license_11_8_0//aar",
        "@com_google_firebase_firebase_common_11_8_0//aar",
        "@com_google_firebase_firebase_common_license_11_8_0//aar",
        "@com_google_firebase_firebase_firestore_11_8_0//aar",
    ],
)

android_library(
    name = "firestore_config_manager",
    data = ["assets/google-services.json"],
    exports = [":firestore_config_manager_impl"],
)

android_binary(
    name = "android_app",
    srcs = glob([
        "MainApplication.java",
        "activities/*.java",
    ]),
    assets = ["assets/google-services.json"],
    assets_dir = "assets/",
    custom_package = "com.google.startupos.examples.android",
    manifest = "AndroidManifest.xml",
    resource_files = glob(["res/**"]),
    deps = [
        ":firestore",
        ":firestore_config_manager",
    ],
)
