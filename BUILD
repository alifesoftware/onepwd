load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kt_android_library", "kt_jvm_library")

PACKAGE = "com.yhsif.onepwd"
MANIFEST = "AndroidManifest.xml"
MANIFEST_VALUES = {"PACKAGE": PACKAGE}

HMAC_SRCS = ["src/com/yhsif/onepwd/HmacMd5.kt"]

kt_jvm_library(
    name = "hmac_md5",
    srcs = HMAC_SRCS,
    visibility = [
        "//tests:__pkg__",
    ],
)

android_binary(
    name = "app",
    custom_package = PACKAGE,
    manifest = MANIFEST,
    manifest_values = MANIFEST_VALUES,
    deps = [
        ":onepwd",
    ],
)

kt_android_library(
    name = "onepwd",
    srcs = glob(
        ["src/**/*.kt"],
        exclude = HMAC_SRCS,
    ),
    custom_package = PACKAGE,
    manifest = MANIFEST,
    resource_files = glob(["res/**/*"]),
    deps = [
        ":hmac_md5",
        ":room",

        "@maven//:androidx_appcompat_appcompat",
        "@maven//:androidx_biometric_biometric",
        "@maven//:androidx_cardview_cardview",
        "@maven//:androidx_core_core_ktx",
        "@maven//:androidx_fragment_fragment_ktx",
        "@maven//:androidx_preference_preference",
        "@maven//:androidx_recyclerview_recyclerview",
        "@maven//:com_google_android_material_material",
    ],
)

java_plugin(
    name = "room_compiler",
    processor_class = "androidx.room.RoomProcessor",
    deps = [
        "@maven//:androidx_room_room_compiler",
    ],
)

java_library(
    name = "room",
    exported_plugins = [
        ":room_compiler",
    ],
    exports = [
        "@maven//:androidx_room_room_runtime",
    ],
)
