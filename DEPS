use_relative_paths = True

deps = {

  "build":      "https://chromium.googlesource.com/chromium/src/build.git",

  "buildtools": "https://chromium.googlesource.com/chromium/buildtools.git",

  "tools/gyp":  "https://chromium.googlesource.com/external/gyp.git",

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
