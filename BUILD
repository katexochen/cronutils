cc_library(
    name = "subprocess",
    srcs = ["subprocess.c"],
    hdrs = ["subprocess.h"],
)

cc_library(
    name = "tempdir",
    srcs = ["tempdir.c"],
    hdrs = ["tempdir.h"],
)

cc_binary(
    name = "runalarm",
    srcs = ["runalarm.c"],
    deps = [":subprocess"],
)

cc_binary(
    name = "runlock",
    srcs = ["runlock.c"],
    deps = [
        ":subprocess",
        ":tempdir",
    ],
)

cc_binary(
    name = "runstat",
    srcs = ["runstat.c"],
    deps = [
        ":subprocess",
        ":tempdir",
    ],
)

filegroup(
    name = "tests",
    srcs = glob(["tests/*.sh"]),
)

filegroup(
    name = "goldens",
    srcs = glob(["tests/*.out"]),
)

sh_test(
    name = "regtest",
    srcs = ["regtest.sh"],
    data = [
        ":goldens",
        ":runalarm",
        ":runlock",
        ":runstat",
        ":tests",
    ],
)
