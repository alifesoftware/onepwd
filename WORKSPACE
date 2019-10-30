workspace(name = "onepwd")

android_sdk_repository(
    name = "androidsdk",
    api_level = 29,
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_KOTLIN_VERSION = "0768fe7355c9d9ac78c60411ac196da394b903d5"

http_archive(
    name = "io_bazel_rules_kotlin",
    strip_prefix = "rules_kotlin-%s" % RULES_KOTLIN_VERSION,
    url = "https://github.com/bazelbuild/rules_kotlin/archive/%s.tar.gz" % RULES_KOTLIN_VERSION,
    sha256 = "0eaa4b8b286054f8cbbec8cca40b0c3fafba7eb82ed55045273ecaf981fb1e1f",
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")

kotlin_repositories()
kt_register_toolchains()


RULES_JVM_EXTERNAL_TAG = "2.9"
RULES_JVM_EXTERNAL_SHA = "e5b97a31a3e8feed91636f42e19b11c49487b85e5de2f387c999ea14d77c7f45"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
    sha256 = RULES_JVM_EXTERNAL_SHA,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")

maven_install(
    artifacts = [
        "com.google.truth:truth:1.0",
        "junit:junit:4.12",

        "androidx.appcompat:appcompat:1.1.0",
        "androidx.biometric:biometric:1.0.0-rc01",
        "androidx.cardview:cardview:1.0.0",
        "androidx.preference:preference:1.1.0",
        "androidx.recyclerview:recyclerview:1.0.0",
        "androidx.sqlite:sqlite:2.0.1",
        "androidx.sqlite:sqlite-framework:2.0.1",
    ],
    repositories = [
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)
