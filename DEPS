vars = {
    "demo": "gn_demo",
    "clang_revision": "e3a7f0e2f9ab566bd9b71fb54fe77e947b061a12",
    "gn_revision": "b79031308cc878488202beb99883ec1f2efd9a6d",
}

deps = {
    Var("demo") + "/buildtools/linux-x64/clang": {
        "packages": [
            {
                "package": "fuchsia/third_party/clang/linux-amd64",
                "version": "git_revision:" + Var("clang_revision"),
            },
        ],
        "condition":
        "host_cpu == x64 and host_os == linux",
        "dep_type":
        "cipd",
    },
    Var("demo") + "/buildtools/mac-x64/clang": {
        "packages": [
            {
                "package": "fuchsia/third_party/clang/mac-amd64",
                "version": "git_revision:" + Var("clang_revision"),
            },
        ],
        # TODO(https://fxbug.dev/73385): Use arm64 toolchain on arm64 when it exists.
        "condition":
        "host_cpu == x64 and host_os == mac or host_cpu == arm64 and host_os == mac",
        "dep_type":
        "cipd",
    },
    Var("demo") + "/buildtools/win-x64/clang": {
        "packages": [
            {
                "package": "fuchsia/third_party/clang/windows-amd64",
                "version": "git_revision:" + Var("clang_revision"),
            },
        ],
        "condition":
        "host_cpu == x64 and host_os == win",
        "dep_type":
        "cipd",
    },
    Var("demo") + "/buildtools/linux-arm64/clang": {
        "packages": [
            {
                "package": "fuchsia/third_party/clang/linux-arm64",
                "version": "git_revision:" + Var("clang_revision"),
            },
        ],
        "condition":
        "host_os == 'linux' and host_cpu == 'arm64'",
        "dep_type":
        "cipd",
    },
    Var("demo") + "/buildtools": {
        "packages": [
            {
                "package": "gn/gn/${{platform}}",
                "version": "git_revision:" + Var("gn_revision"),
            },
        ],
        "dep_type":
        "cipd",
    },
}

hooks = [
    {
        'name': 'buildtools',
        'pattern': '.',
        'action': ['python3',
                   Var("demo") + '/tools/buildtools/update.py'],
    },
]