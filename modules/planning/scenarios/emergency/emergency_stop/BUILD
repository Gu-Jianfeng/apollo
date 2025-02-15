load("//tools:cpplint.bzl", "cpplint")

package(default_visibility = ["//visibility:public"])

cc_library(
    name = "emergency_stop_scenario",
    srcs = [
        "emergency_stop_scenario.cc",
        "stage_approach.cc",
        "stage_standby.cc",
    ],
    hdrs = [
        "emergency_stop_scenario.h",
        "stage_approach.h",
        "stage_standby.h",
    ],
    copts = ["-DMODULE_NAME=\\\"planning\\\""],
    deps = [
        "//cyber/common:log",
        "//external:gflags",
        "//modules/common/util:factory",
        "//modules/common/vehicle_state:vehicle_state_provider",
        "//modules/planning/common:planning_common",
        "//modules/planning/common/util:common_lib",
        "//modules/planning/common/util:util_lib",
        "//modules/planning/proto:planning_proto",
        "//modules/planning/scenarios:scenario",
        "//modules/planning/scenarios/util:scenario_util_lib",
        "@eigen",
    ],
)

cc_test(
    name = "emergency_stop_scenario_test",
    size = "small",
    srcs = [
        "emergency_stop_scenario_test.cc",
    ],
    data = [
        "//modules/planning:planning_conf",
    ],
    deps = [
        ":emergency_stop_scenario",
        "@gtest//:main",
    ],
)

cc_test(
    name = "stage_approach_test",
    size = "small",
    srcs = [
        "stage_approach_test.cc",
    ],
    data = [
        "//modules/planning:planning_conf",
    ],
    deps = [
        ":emergency_stop_scenario",
        "@gtest//:main",
    ],
)

cc_test(
    name = "stage_standby_test",
    size = "small",
    srcs = [
        "stage_standby_test.cc",
    ],
    data = [
        "//modules/planning:planning_conf",
    ],
    deps = [
        ":emergency_stop_scenario",
        "@gtest//:main",
    ],
)

cpplint()
