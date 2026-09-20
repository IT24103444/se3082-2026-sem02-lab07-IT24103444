MPICC = mpicc
MPIRUN = mpirun --oversubscribe
NP = 4

BCAST = sum_bcast
SCATTER = sum_scatter
GATHER = sum_gather
REDUCE = sum_reduce
ALLREDUCE = sum_allreduce
SCAN = sum_scan

all: $(BCAST) $(SCATTER) $(GATHER) $(REDUCE) $(ALLREDUCE) $(SCAN)

$(BCAST): ../Exercise01/sum_bcast.c
	$(MPICC) -o $(BCAST) ../Exercise01/sum_bcast.c

$(SCATTER): ../Exercise02/sum_scatter.c
	$(MPICC) -o $(SCATTER) ../Exercise02/sum_scatter.c

$(GATHER): ../Exercise03/sum_gather.c
	$(MPICC) -o $(GATHER) ../Exercise03/sum_gather.c

$(REDUCE): ../Exercise04/sum_reduce.c
	$(MPICC) -o $(REDUCE) ../Exercise04/sum_reduce.c

$(ALLREDUCE): ../Exercise05/sum_allreduce.c
	$(MPICC) -o $(ALLREDUCE) ../Exercise05/sum_allreduce.c

$(SCAN): ../Exercise06/sum_scan.c
	$(MPICC) -o $(SCAN) ../Exercise06/sum_scan.c

run: all
	$(MPIRUN) -np $(NP) ./$(BCAST)
	$(MPIRUN) -np $(NP) ./$(SCATTER)
	$(MPIRUN) -np $(NP) ./$(GATHER)
	$(MPIRUN) -np $(NP) ./$(REDUCE)
	$(MPIRUN) -np $(NP) ./$(ALLREDUCE)
	$(MPIRUN) -np $(NP) ./$(SCAN)

clean:
	rm -f $(BCAST) $(SCATTER) $(GATHER) $(REDUCE) $(ALLREDUCE) $(SCAN)
