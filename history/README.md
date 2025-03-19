# Blocks History STF Test Vectors

Both JSON and SCALE formats conform to the JAM ASN.1 [schema](../jam-types-asn/jam-types.asn)
and this subsystem STF specific [schema](./history.asn).

## Input Origin

**While the origin of the input data is irrelevant for these test vectors and has
been randomly generated**, it is important to outline the semantics of each input,
as they play a crucial role in updating the state.

- `header_hash`: The hash of the current block header being processed.
- `parent_state_root` ($H_r$): The state root of the parent block, as found in the current block header.
- `accumulate_root`: The Merkle root resulting from the accumulation process.
- `work_packages`: A sequence of work package hashes.

## MMR

The tests presented here are relatively straightforward, with the most
significant aspect being the MMR (Merkle Mountain Range) update, which relies on
the input `accumulate_root`.

## Vectors

- [progress_blocks_history-1](data/progress_blocks_history-1.json) 🟢 
  - Empty history queue.
- [progress_blocks_history-2](data/progress_blocks_history-2.json) 🟢 
  - Not empty nor full history queue.
- [progress_blocks_history-3](data/progress_blocks_history-3.json) 🟢 
  - Fill the history queue.
- [progress_blocks_history-4](data/progress_blocks_history-4.json) 🟢 
  - Shift the history queue.
