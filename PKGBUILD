# SPDX-License-Identifier: AGPL-3.0

#    -----------------------------------------------------
#    Copyright © 2024, 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    -----------------------------------------------------
#
#    This program is free software: you can redistribute
#    it and/or modify it under the terms of the
#    GNU Affero General Public License as published by
#    the Free Software Foundation, either version 3 of
#    the License, or (at your option) any later version.
#
#    This program is distributed in the hope that it
#    will be useful, but WITHOUT ANY WARRANTY;
#    without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.
#    See the GNU Affero General Public License for
#    more details.
#
#    You should have received a copy of the
#    GNU Affero General Public License
#    along with this program.
#    If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>

_os="$(
  uname \
    -o)"
_evmfs_available="$(
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
_node="nodejs"
_node_pkg="${_node}"
if [[ "${_os}" == "Android" ]]; then
  _node_pkg="${_node}-lts"
  _node_pkg="${_node}"
fi
if [[ ! -v "_npm" ]]; then
  _npm="false"
fi
if [[ ! -v "_make" ]]; then
  _make="false"
fi
if [[ ! -v "_git" ]]; then
  _git="false"
fi
if [[ ! -v "_git_service" ]]; then
  _git_service="github"
fi
if [[ ! -v "_git_http" ]]; then
  _git_http="${_git_service}"
fi
_archive_format="tgz"
if [[ ! -v "${_archive_format}" ]]; then
  if [[ "${_npm}" == "false" ]]; then
    if [[ "${_git_http}" == "github" ]]; then
      _archive_format="zip"
    fi
  fi
fi
_pkg=libcoreutils
pkgbase="nodejs-${_pkg}"
pkgname=(
  "${pkgbase}"
)
_pkgdesc=(
  "Browser-compatible and Node.js"
  "GNU coreutils' library"
  "Javascript partial implementation."
  "Part of senzacoreutils."
)
pkgdesc="${_pkgdesc[*]}"
_commit="fa7a8e78abd2d14fa6474a6f710945f2568beb97"
_pkgver="0.0.26"
pkgver="${_pkgver}"
pkgrel=3
arch=(
  'any'
)
_http="https://${_git_http}.com"
_ns="themartiancompany"
url="${_http}/${_ns}/${_pkg}"
license=(
  'AGPL3'
)
depends=(
  "${_node}"
)
provides=(
  "${_pkg}=${pkgver}"
)
makedepends=(
  "npm"
)
if [[ "${_npm}" == "true" ]]; then
  makedepends+=(
    "npm"
    "findutils"
  )
elif [[ "${_npm}" == "false" ]]; then
  if [[ "${_make}" == "false" ]]; then
    makedepends+=(
      "npm"
    )
  fi
fi
if [[ "${_git}" == "true" ]]; then
  makedepends+=(
    "git"
  )
fi
if [[ "${_make}" == "true" ]]; then
  makedepends+=(
    "make"
  )
fi
if [[ "${_npm}" == "true" ]]; then
  _tag="${pkgver}"
  _tag_name="pkgver"
elif [[ "${_npm}" == "false" ]]; then
  _tag="${_commit}"
  _tag_name="commit"
fi
_tarname="${_pkg}-${_tag}"
_npm_tarname="${_ns}-${_pkg}-${_tag}"
_tarfile="${_tarname}.${_archive_format}"
_npm_tarfile="${_npm_tarname}.${_archive_format}"
_sum="489e38184069ee6e81d1f0dfc3fd2efaeb49df787c5a54addfe256e61ab50856"
_sig_sum="boh"
_bundle_sum="boh"
_bundle_sig_sum="boh"
_npm_sum="58020e57615d558be9fd786535514cadd09ec7d4574e7842a30013df1cdf1c3c"
_npm_sig_sum="boh"
# Truocolo
_evmfs_ns="0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_evmfs_uri="${_evmfs_dir}/${_sum}"
_evmfs_src="${_tarfile}::${_evmfs_uri}"
_bundle_uri="${_evmfs_dir}/${_bundle_sum}"
_bundle_src="${_tarfile}::${_bundle_uri}"
_evmfs_npm_uri="${_evmfs_dir}/${_npm_sum}"
_evmfs_npm_src="${_tarfile}::${_evmfs_npm_uri}"
_evmfs_sig_uri="${_evmfs_dir}/${_sig_sum}"
_evmfs_sig_src="${_tarfile}.sig::${_evmfs_sig_uri}"
_bundle_sig_uri="${_evmfs_dir}/${_bundle_sig_sum}"
_bundle_sig_src="${_tarfile}.sig::${_bundle_sig_uri}"
_npm_sig_uri="${_evmfs_dir}/${_npm_sig_sum}"
_npm_sig_src="${_tarfile}.sig::${_npm_sig_uri}"
_npm_http="http://registry.npmjs.org"
source=()
sha256sums=()
if [[ "${_evmfs}" == "true" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_evmfs_npm_uri}"
    _sum="${_evmfs_npm_sum}"
    _sig_src="${_evmfs_npm_uri}"
    _sig_sum="${_npm_sig_sum}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_git}" == "true" ]]; then
      _uri="${_bundle_uri}"
      _sum="${_bundle_sum}"
      _sig_src="${_bundle_sig_src}"
      _sig_sum="${_bundle_sig_sum}"
    elif [[ "${_git}" == "false" ]]; then
      _uri="${_evmfs_uri}"
      _sig_src="${_evmfs_sig_src}"
    fi
  fi
  source+=(
    "${_sig_src}"
  )
  sha256sums+=(
    "${_sig_sum}"
  )
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_npm}" == "true" ]]; then
    _uri="${_npm_http}/${_pkg}/-/${_tarfile}"
  elif [[ "${_npm}" == "false" ]]; then
    if [[ "${_tag_name}" == 'pkgver' ]]; then
      if [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/archive/refs/tags/${_tag}.${_archive_format}"
      fi
    elif [[ "${_tag_name}" == "commit" ]]; then
      if [[ "${_git_http}" == "github" ]]; then
        _uri="${url}/archive/${_commit}.${_archive_format}"
      elif [[ "${_git_http}" == "gitlab" ]]; then
        _uri="${url}/-/archive/${_commit}/${_tarname}.${_archive_format}"
      fi
    fi
  fi
fi
if [[ "${_npm}" == "true" ]]; then
  _tarfile="${_npm_tarfile}"
fi
_src="${_tarfile}::${_uri}"
source+=(
  "${_src}"
)
sha256sums+=(
  "${_sum}"
)
if [[ "${_npm}" == "true" ]]; then
  noextract=(
    "${_tarfile}"
  )
fi
validpgpkeys=(
  # Truocolo
  #   <truocolo@aol.com>
  '97E989E6CF1D2C7F7A41FF9F95684DBE23D6A3E9'
  'DD6732B02E6C88E9E27E2E0D5FC6652B9D9A6C01'
  #   <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
  'F690CBC17BD1F53557290AF51FC17D540D0ADEED'
  # Pellegrino Prevete (dvorak)
  #   <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
  '12D8E3D7888F741E89F86EE0FEC8567A644F1D16'
)

build() {
  local \
    _files=()
  _files+=(
    "AUTHORS.rst"
    "COPYING"
    "README.md"
    "base64"
    "base64.webpack.config.cjs"
    "dist"
    "eslint.config.mjs"
    "fs-worker.webpack.config.cjs"
    "libbase64"
    "libbase64.webpack.config.cjs"
    "libcoreutils"
    "man"
    "package.json"
    "serve.json"
    "webpack.config.cjs"
  )
  if [[ "${_npm}" == "false" ]]; then
    if [[ "${_make}" == "false" ]]; then
      cd \
        "${_tarname}"
      mkdir \
        -p \
        "build"
      cp \
        -r \
        "${_files[@]}" \
        "build"
      cd \
        "build"
      npm \
        install
      npm \
        pack
      mv \
        "${_ns}-${_pkg}-${_pkgver}.tgz" \
        "${srcdir}"
    fi
  fi
}

package_nodejs-libcoreutils() {
  local \
    _make_opts=() \
    _npm_opts=() \
    _find_opts=()
  if [[ "${_make}" == "true" ]]; then
    _make_opts+=(
      DESTDIR="${pkgdir}"
      PREFIX="/usr"
    )
    make \
      "${_make_opts[@]}" \
      install
  elif [[ "${_make}" == "false" ]]; then
    _npm_opts=(
      -g 
      # --user 
      #   root 
      --prefix 
        "${pkgdir}/usr"
    )
    find_opts+=(
      -type
        "d"
      -exec
        chmod
          755
          '{}'
          +
    )
    npm \
      install \
      "${_npm_opts[@]}" \
      "${srcdir}/${_ns}-${_pkg}-${_pkgver}.tgz"
    rm \
      -fr \
        "${pkgdir}/usr/etc"
    # Fix npm derp
    find \
      "${pkgdir}/usr" \
      "${_find_opts[@]}"
  fi
}

# vim:set sw=2 sts=-1 et:
