# OSI Model – Overview

## What this is
A conceptual model that explains how network communication is divided into layers.

## Layers (top to bottom)
- Application (Provides applications network access)
- Presentation (Formats application data)
- Session (Establishes, maintains and terminates session communication)
- Transport (TCP: connection oriented, sequnecing and segmentation,
  reliable delivery vs UDP: connectionless, Best effort delivery)
- Network (routing, logical addressing)
- Data Link (flow, control, acknowledgements, error detection, determines
  access to media)(LLC, MAC)
- Physical (electrical and mechanical characteristics)

## mnemonic for remembering the layers
All people seem to need data processing

## Layer Characteristics
- Upper layers support application functionality
- Lower layers support network functionality
- 
## Why layers exist
- Separation of concerns
- Easier troubleshooting
- Standardization

## Still unclear
- What exactly happens at each layer (Watching the lesson again reinforced
  some concepts including what happens at each layer. Added that to layers)
- Protocols at each layer were listed but they will be discussed later.
