---
description: /blockchain/{asset}/blocks
---

# Blocks

Atlas/UBDM employs the universal concept of blocks which have the following fields in the response for the **Blocks** endpoint:

| Field                  | Description                                                                                                      |
| ---------------------- | ---------------------------------------------------------------------------------------------------------------- |
| block\_hash            | Hash of that block (unique per block)                                                                            |
| parent\_block\_hash    | Hash of the parent block (set to a string of 65 zeros for Genesis blocks)                                        |
| height                 | Height of that block (number of confirmed blocks since Genesis block)                                            |
| consensus\_time        | [Consensus timestamp](../../on-chain-data/atlas-overview.md#consensus-timestamp); always increases monotonically |
| miner\_time            | [Miner/producer timestamp](../../on-chain-data/atlas-overview.md#miner-timestamps)                               |
| n\_transactions        | Number of transactions                                                                                           |
| n\_balance updates     | Number of balance updates                                                                                        |
| difficulty             | Difficulty of the block                                                                                          |
| physical\_size         | The physical size of a block in bytes                                                                            |
| consensus\_size        | The stripped size of the block with Segregated Witness (signature) data                                          |
| consensus\_size\_limit | The size limit of a block in weight units                                                                        |
