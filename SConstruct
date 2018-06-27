# -*- coding: utf-8 -*-
#-------------------------------------------------------------------------#
#   Copyright (C) 2018 by Christoph Thelen                                #
#   doc_bacardi@users.sourceforge.net                                     #
#                                                                         #
#   This program is free software; you can redistribute it and/or modify  #
#   it under the terms of the GNU General Public License as published by  #
#   the Free Software Foundation; either version 2 of the License, or     #
#   (at your option) any later version.                                   #
#                                                                         #
#   This program is distributed in the hope that it will be useful,       #
#   but WITHOUT ANY WARRANTY; without even the implied warranty of        #
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the         #
#   GNU General Public License for more details.                          #
#                                                                         #
#   You should have received a copy of the GNU General Public License     #
#   along with this program; if not, write to the                         #
#   Free Software Foundation, Inc.,                                       #
#   59 Temple Place - Suite 330, Boston, MA  02111-1307, USA.             #
#-------------------------------------------------------------------------#


#----------------------------------------------------------------------------
#
# Set up the Muhkuh Build System.
#

SConscript('mbs/SConscript')
Import('atEnv')

import os.path
import tarfile


#----------------------------------------------------------------------------
#
# Depack the source archive.
#
tSrcArchive = tarfile.open('lua-log-0.1.6.tar.gz', 'r')
tSrcArchive.extractall('targets/depack')
tSrcArchive.close()
strDepackPath = 'targets/depack/lua-log-0.1.6/'

#----------------------------------------------------------------------------
#
# Build the artifacts.
#

strGroup = 'com.github.moteus'
strModule = 'lua-log'

# Split the group by dots.
aGroup = strGroup.split('.')
# Build the path for all artifacts.
strModulePath = 'targets/jonchki/repository/%s/%s/%s' % ('/'.join(aGroup), strModule, PROJECT_VERSION)

# Set the name of the artifact.
strArtifact = 'lua-log'

tArcList = atEnv.DEFAULT.ArchiveList('zip')

tArcList.AddFiles('',
                    'installer/install.lua')

tArcList.AddFiles('lua/',
                  os.path.join(strDepackPath, 'lua/log.lua'))

tArcList.AddFiles('lua/log/formatter/',
                  os.path.join(strDepackPath, 'lua/log/formatter/concat.lua'),
                  os.path.join(strDepackPath, 'lua/log/formatter/default.lua'),
                  os.path.join(strDepackPath, 'lua/log/formatter/format.lua'),
                  os.path.join(strDepackPath, 'lua/log/formatter/mix.lua'),
                  os.path.join(strDepackPath, 'lua/log/formatter/pformat.lua'))

tArcList.AddFiles('lua/log/logformat/',
                  os.path.join(strDepackPath, 'lua/log/logformat/default.lua'),
                  os.path.join(strDepackPath, 'lua/log/logformat/proxy.lua'),
                  os.path.join(strDepackPath, 'lua/log/logformat/syslog.lua'))

tArcList.AddFiles('lua/log/logformat/proxy/',
                  os.path.join(strDepackPath, 'lua/log/logformat/proxy/pack.lua'))

tArcList.AddFiles('lua/log/writer/',
                  os.path.join(strDepackPath, 'lua/log/writer/console.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/file.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/filter.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/format.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/list.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/prefix.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/stderr.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/stdout.lua'))

tArcList.AddFiles('lua/log/writer/async/',
                  os.path.join(strDepackPath, 'lua/log/writer/async/lane.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/async/udp.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/async/zmq.lua'))

tArcList.AddFiles('lua/log/writer/async/_private/',
                  os.path.join(strDepackPath, 'lua/log/writer/async/_private/server.lua'))

tArcList.AddFiles('lua/log/writer/async/server/',
                  os.path.join(strDepackPath, 'lua/log/writer/async/server/lane.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/async/server/udp.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/async/server/zmq.lua'))

tArcList.AddFiles('lua/log/writer/console/',
                  os.path.join(strDepackPath, 'lua/log/writer/console/color.lua'))

tArcList.AddFiles('lua/log/writer/file/',
                  os.path.join(strDepackPath, 'lua/log/writer/file/by_day.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/file/roll.lua'))

tArcList.AddFiles('lua/log/writer/file/private/',
                  os.path.join(strDepackPath, 'lua/log/writer/file/private/impl.lua'))

tArcList.AddFiles('lua/log/writer/filter/lvl/',
                  os.path.join(strDepackPath, 'lua/log/writer/filter/lvl/eq.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/filter/lvl/le.lua'))

tArcList.AddFiles('lua/log/writer/net/',
                  os.path.join(strDepackPath, 'lua/log/writer/net/smtp.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/net/udp.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/net/zmq.lua'))

tArcList.AddFiles('lua/log/writer/net/server/',
                  os.path.join(strDepackPath, 'lua/log/writer/net/server/udp.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/net/server/zmq.lua'))

tArcList.AddFiles('lua/log/writer/net/zmq/',
                  os.path.join(strDepackPath, 'lua/log/writer/net/zmq/pub.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/net/zmq/push.lua'))

tArcList.AddFiles('lua/log/writer/net/zmq/_private/',
                  os.path.join(strDepackPath, 'lua/log/writer/net/zmq/_private/compat.lua'),
                  os.path.join(strDepackPath, 'lua/log/writer/net/zmq/_private/impl.lua'))

tArcList.AddFiles('lua/log/writer/net/zmq/srv/',
                  os.path.join(strDepackPath, 'lua/log/writer/net/zmq/srv/pub.lua'))


tArtifact = atEnv.DEFAULT.Archive(os.path.join(strModulePath, '%s-%s.zip' % (strArtifact, PROJECT_VERSION)), None, ARCHIVE_CONTENTS = tArcList)
tArtifactHash = atEnv.DEFAULT.Hash('%s.hash' % tArtifact[0].get_path(), tArtifact[0].get_path(), HASH_ALGORITHM='md5,sha1,sha224,sha256,sha384,sha512', HASH_TEMPLATE='${ID_UC}:${HASH}\n')
tConfiguration = atEnv.DEFAULT.Version(os.path.join(strModulePath, '%s-%s.xml' % (strArtifact, PROJECT_VERSION)), 'installer/%s.xml' % strModule)
tConfigurationHash = atEnv.DEFAULT.Hash('%s.hash' % tConfiguration[0].get_path(), tConfiguration[0].get_path(), HASH_ALGORITHM='md5,sha1,sha224,sha256,sha384,sha512', HASH_TEMPLATE='${ID_UC}:${HASH}\n')
tArtifactPom = atEnv.DEFAULT.ArtifactVersion(os.path.join(strModulePath, '%s-%s.pom' % (strArtifact, PROJECT_VERSION)), 'installer/pom.xml')
