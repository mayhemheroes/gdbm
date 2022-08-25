# Copyright 2021 Google Inc.
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
#
################################################################################

FROM gcr.io/oss-fuzz-base/base-builder
RUN apt-get -qq update && apt-get install -qq build-essential git autopoint automake autoconf bison flex libtool texinfo gettext
COPY . gdbm
RUN rm -rf gdbm/mayhem
WORKDIR gdbm
COPY mayhem/build.sh $SRC/

ENV FUZZING_LANGUAGE=c
RUN compile
RUN chmod +x /out/gdbm_fuzzer
