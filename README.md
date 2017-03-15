# tez-build
build tez

sudo apt-get install mvn

wget -c https://github.com/google/protobuf/releases/download/v2.5.0/protobuf-2.5.0.tar.bz2

tar -xvf protobuf-2.5.0.tar.bz2

cd protobuf-2.5.0

./configure

make -j8

sudo make install 

sudo ldconfig

cd ..

git clone https://github.com/apache/tez && cd tez

mvn package -DskipTest -Phadoop28 -Dhadoop.version=2.9.0-SNAPSHOT -DskipTests -Pazure  -pl '!tez-ui'
