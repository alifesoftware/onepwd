workspace(name = "onepwd")

android_sdk_repository(
    name = "androidsdk",
    api_level = 28,
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_KOTLIN_VERSION = "4c71740a1b63b785fc90afd8d4d4d5bfda527107"
http_archive(
    name = "io_bazel_rules_kotlin",
    strip_prefix = "rules_kotlin-%s" % RULES_KOTLIN_VERSION,
    url = "https://github.com/bazelbuild/rules_kotlin/archive/%s.tar.gz" % RULES_KOTLIN_VERSION,
    sha256 = "249ad2683cff70c1336d3e6b35b1ba1890d5ff5a820e3606ad4103a023bf794b",
)
load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")

kotlin_repositories()
kt_register_toolchains()

RULES_JVM_EXTERNAL_TAG = "2.0.1"
http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
    sha256 = "55e8d3951647ae3dffde22b4f7f8dee11b3f70f3f89424713debd7076197eaca",
)
load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "com.google.truth:truth:0.43",
        "junit:junit:4.12",

        "androidx.appcompat:appcompat:1.0.2",
        "androidx.cardview:cardview:1.0.0",
        "androidx.preference:preference:1.0.0",
        "androidx.recyclerview:recyclerview:1.0.0",
        "androidx.sqlite:sqlite:2.0.1",
        "androidx.sqlite:sqlite-framework:2.0.1",
    ],
    repositories = [
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)
