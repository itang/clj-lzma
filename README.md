# clj-lzma

A Clojure wrapper for lzma-java.

## Install

local install

## Usage

        (ns clj-lzma.core-test
          (:require [clojure.test :refer :all]
                    [clj-lzma.core :refer :all]))

        (def message "hello,world")

        (def input-file "./target/hello.txt")
        (def compress-file "./target/hello.lzf")
        (def decompress-file "./target/hello.de.txt")

        (deftest compress-test
          (testing "compress"
            (spit input-file message)
            (is (= message
                   (do (compress input-file compress-file)
                       (decompress compress-file decompress-file)
                       (slurp decompress-file))))))

## License

Copyright © 2013 itang

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
