ROOTFLAGS=-g -I$ROOTSYS/include -L$ROOTSYS/lib `root-config --cflags` `root-config --libs`

SAMPLE=gg_HH_bbbb_SM
TAG=analysisNtuples_final

.PHONY: clean test

build_objects: build_objects.cpp include/*.h
	g++ build_objects.cpp -o build_objects -Iinclude $(ROOTFLAGS)

test:
	./build_objects root://cmseos.fnal.gov//store/user/cmsdas/2022/long_exercises/DoubleHiggs/$(TAG)/dasformat/dasntuples_$(SAMPLE).root test_$(SAMPLE).root 0 0

clean:
	rm -f build_objects