## Makefile, static linking. Pythia8 is fetched and built
## automatically.

homeDIR = $(shell pwd)

CXX      := g++

CXXFLAGS := -O3 -I$(pythia8path)/include -I$(pythia8path)/include/Pythia8/ -I$(fastjetpath)/include -I$(hepmcpath)/include
LDFLAGS  := -L$(pythia8path)/lib/ -L$(pythia8path)/lib -Wl,-rpath,$(pythia8path)/lib -L$(fastjetpath)/lib -Wl,-rpath,$(fastjetpath)/lib -L$(hepmcpath)/lib -Wl,-rpath,$(hepmcpath)/lib
XMLDOC   := $(pythia8path)/share/Pythia8/xmldoc

all: main_atlas_susy_2016_08.exe


clean:
	rm main_atlas_susy_2016_08.exe

main_atlas_susy_2016_08.exe: recastCode/main_atlas_susy_2016_08.cc recastCode/helperFunctions.h recastCode/dataReader.h
	echo $(XMLDOC) > xml.doc
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o $@ recastCode/main_atlas_susy_2016_08.cc -lpythia8 -ldl -DGZIPSUPPORT -lz -lfastjet


main_atlas_susy_2016_08_cutFlow.exe: recastCode/main_atlas_susy_2016_08_cutFlow.cc recastCode/helperFunctions.h recastCode/dataReader.h
	echo $(XMLDOC) > xml.doc
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o $@ recastCode/main_atlas_susy_2016_08_cutFlow.cc -lpythia8 -ldl -DGZIPSUPPORT -lz -lfastjet -lHepMC


main_atlas_susy_2016_08_merged_cutFlow.exe: recastCode/main_atlas_susy_2016_08_merged_cutFlow.cc recastCode/helperFunctions.h recastCode/dataReader.h
	echo $(XMLDOC) > xml.doc
	$(CXX) $(CXXFLAGS) $(LDFLAGS) -o $@ recastCode/main_atlas_susy_2016_08_merged_cutFlow.cc -lpythia8 -ldl -DGZIPSUPPORT -lz -lfastjet -lHepMC

