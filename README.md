# Counting-k-mers
package main

import "fmt"

func countkmers(sequence string, k int) map[string]int {
	var kmers = make(map[string]int)

	if k > len(sequence) || k <= 0 {
		return kmers
	}

	for i := 0; i < len(sequence) - k + 1; i++ {
		var kmer = sequence[i:i+k]
		kmers[kmer]++
	}

	return kmers
}

func main() {
	fmt.Println(countkmers("ACGAGGTACGA", 3))
}
