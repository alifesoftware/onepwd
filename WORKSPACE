workspace(name = "onepwd")

android_sdk_repository(
    name = "androidsdk",
    api_level = 28,
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

RULES_KOTLIN_VERSION = "da1232eda2ef90d4375e2d1677b32c7ddf09e8a1"
http_archive(
    name = "io_bazel_rules_kotlin",
    strip_prefix = "rules_kotlin-%s" % RULES_KOTLIN_VERSION,
    url = "https://github.com/bazelbuild/rules_kotlin/archive/%s.tar.gz" % RULES_KOTLIN_VERSION,
    sha256 = "0bbb0e5e536f0c775f37bded59d4f8cfb8556e6c3d926fcc0f58bf3489bff470",
)
load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")

kotlin_repositories()
kt_register_toolchains()

RULES_JVM_EXTERNAL_TAG = "1.1"
http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    url = "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
    sha256 = "ade316ec98ba0769bb1189b345d9877de99dd1b1e82f5a649d6ccbcb8da51c1f",
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

        # indirect deps:
        "androidx.core:core:1.0.1",
        "androidx.drawerlayout:drawerlayout:1.0.0",
        "androidx.fragment:fragment:1.0.0",
        "androidx.lifecycle:lifecycle-common:2.0.0",
        "androidx.lifecycle:lifecycle-viewmodel:2.0.0",
    ],
    repositories = [
        "https://maven.google.com",
        "https://repo1.maven.org/maven2",
    ],
)
