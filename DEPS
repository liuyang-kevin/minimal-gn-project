use_relative_paths = True

deps = {
    "build": "https://chromium.googlesource.com/chromium/src/build",
    "buildtools": "https://chromium.googlesource.com/chromium/src/buildtools",
    "tools/gyp": "https://chromium.googlesource.com/external/gyp",
    'tools/gn': {
        'packages': [
            {
                'package': 'gn/gn/${{platform}}',
                'version': 'git_revision:b79031308cc878488202beb99883ec1f2efd9a6d'
            },
        ],
        'dep_type': 'cipd',
    }
}

hooks = [{
    'action': [
        'download_from_google_storage',
        '--no_resume',
        '--platform=win32',
        '--no_auth',
        '--bucket',
        'chromium-gn',
        '-s',
        'minimal-gn-project/buildtools/win/gn.exe.sha1'
    ],
    'pattern': '.',
    'name': 'gn_win'
}, {
    'action': [
        'download_from_google_storage',
        '--no_resume',
        '--platform=darwin',
        '--no_auth',
        '--bucket',
        'chromium-gn',
        '-s',
        'minimal-gn-project/buildtools/mac/gn.sha1'
    ],
    'pattern': '.',
    'name': 'gn_mac'
}, {
    'action': [
        'download_from_google_storage',
        '--no_resume',
        '--platform=linux*',
        '--no_auth',
        '--bucket',
        'chromium-gn',
        '-s',
        'minimal-gn-project/buildtools/linux32/gn.sha1'
    ],
    'pattern': '.',
    'name': 'gn_linux32'
}, {
    'action': [
        'download_from_google_storage',
        '--no_resume',
        '--platform=linux*',
        '--no_auth',
        '--bucket',
        'chromium-gn',
        '-s',
        'minimal-gn-project/buildtools/linux64/gn.sha1'
    ],
    'pattern': '.',
    'name': 'gn_linux64'
}]
