workspace(name = "onepwd")

android_sdk_repository(
    name = "androidsdk",
    api_level = 29,
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")


STARDOC_TAG = "0.4.0"
STARDOC_SHA = "36b8d6c2260068b9ff82faea2f7add164bf3436eac9ba3ec14809f335346d66a"

http_archive(
    name = "io_bazel_stardoc",
    strip_prefix = "stardoc-%s" % STARDOC_TAG,
    urls = [
        "https://github.com/bazelbuild/stardoc/archive/%s.zip" % STARDOC_TAG,
    ],
    sha256 = STARDOC_SHA,
)

load("@io_bazel_stardoc//:setup.bzl", "stardoc_repositories")
stardoc_repositories()


RULES_PROTO_VERSION = "97d8af4dc474595af3900dd85cb3a29ad28cc313"
RULES_PROTO_SHA = "602e7161d9195e50246177e7c55b2f39950a9cf7366f74ed5f22fd45750cd208"

http_archive(
    name = "rules_proto",
    strip_prefix = "rules_proto-%s" % RULES_PROTO_VERSION,
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_proto/archive/%s.tar.gz" % RULES_PROTO_VERSION,
        "https://github.com/bazelbuild/rules_proto/archive/%s.tar.gz" % RULES_PROTO_VERSION,
    ],
    sha256 = RULES_PROTO_SHA,
)

load("@rules_proto//proto:repositories.bzl", "rules_proto_dependencies", "rules_proto_toolchains")
rules_proto_dependencies()
rules_proto_toolchains()


RULES_PKG_TAG = "0.2.6"
RULES_PKG_SHA = "aeca78988341a2ee1ba097641056d168320ecc51372ef7ff8e64b139516a4937"

http_archive(
    name = "rules_pkg",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_pkg/releases/download/%s/rules_pkg-%s.tar.gz" % (RULES_PKG_TAG, RULES_PKG_TAG),
        "https://github.com/bazelbuild/rules_pkg/releases/download/%s/rules_pkg-%s.tar.gz" % (RULES_PKG_TAG, RULES_PKG_TAG),
    ],
    sha256 = RULES_PKG_SHA,
)

load("@rules_pkg//:deps.bzl", "rules_pkg_dependencies")
rules_pkg_dependencies()


RULES_JVM_EXTERNAL_TAG = "3.3"
RULES_JVM_EXTERNAL_SHA = "d85951a92c0908c80bd8551002d66cb23c3434409c814179c0ff026b53544dab"

http_archive(
    name = "rules_jvm_external",
    strip_prefix = "rules_jvm_external-%s" % RULES_JVM_EXTERNAL_TAG,
    urls = [
        "https://github.com/bazelbuild/rules_jvm_external/archive/%s.zip" % RULES_JVM_EXTERNAL_TAG,
    ],
    sha256 = RULES_JVM_EXTERNAL_SHA,
)

load("@rules_jvm_external//:defs.bzl", "maven_install")
maven_install(
    artifacts = [
        "com.google.truth:truth:1.0.1",
        "junit:junit:4.13",

        "androidx.appcompat:appcompat:1.2.0",
        "androidx.biometric:biometric:1.0.1",
        "androidx.cardview:cardview:1.0.0",
        "androidx.core:core-ktx:1.3.1",
        "androidx.fragment:fragment-ktx:1.2.4",
        "androidx.preference:preference:1.1.1",
        "androidx.recyclerview:recyclerview:1.1.0",
        "androidx.room:room-compiler:2.2.5",
        "androidx.room:room-runtime:2.2.5",
        "com.google.android.material:material:1.2.0",
    ],
    repositories = [
        "https://maven.google.com",
        "https://jcenter.bintray.com/",
        "https://repo1.maven.org/maven2",
    ],
    maven_install_json = "@onepwd//:maven_install.json",
)


load("@maven//:defs.bzl", "pinned_maven_install")
pinned_maven_install()

RULES_KOTLIN_TAG = "legacy-1.4.0-rc3"
RULES_KOTLIN_SHA = "c47961a5021e72948c61874ddfc9fd21959ec2742aa67878b94f47308487d773"

http_archive(
    name = "io_bazel_rules_kotlin",
    strip_prefix = "rules_kotlin-%s" % RULES_KOTLIN_TAG,
    urls = [
        "https://github.com/bazelbuild/rules_kotlin/archive/%s.tar.gz" % RULES_KOTLIN_TAG,
    ],
    sha256 = RULES_KOTLIN_SHA,
)

load("@io_bazel_rules_kotlin//kotlin:kotlin.bzl", "kotlin_repositories", "kt_register_toolchains")
kotlin_repositories()
kt_register_toolchains()
