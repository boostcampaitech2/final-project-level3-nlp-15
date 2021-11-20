# Pokemon-DALLE

DALL-E model adapted to Pokemon image generation domain.

[👉 Notion Work Space](https://www.notion.so/Pokemon-Dall-E-de132b5ce0df4456af309cf336f77bec)

### 목표

- Descriptive Text → Image Generation Model adapted to Pokemon Domain.
- 3~4줄의 내용 → 64 x 64 pixel 혹은 225 x 225 pixel
- **프로젝트 막바지에 BART → VQGAN으로 생성한 포켓몬 이미지들을 NFT화하고 등록하기**

### 데이터셋

```
지금의 포켓몬스터의 디자인이 나오기까지 디자인을 담당하는 스기모리 켄이 약 300여가지의 스케치를 그렸다. 그 후 사내 인기투표까지 하면서 다시 그려낸 150여마리의 포켓몬을 엄선하게 되었다. 포켓몬의 수는 시리즈가 나올 때마다 100마리, 135마리, 107마리, 156마리, 72마리, 86마리, 2마리[12], 82마리, 7마리[13]가 추가되어 8세대까지 총 898마리가 되었다.
```

- [Pokedex 898건](https://github.com/veekun/pokedex) | [데이터 예시](https://veekun.com/dex/pokemon/pikachu)
  - Pokemon Shapes: wings, squiggle, fish...
  - 한국어도 있음.
  - MIT License만 지키면 맘대로 사용 가능함.
- [PokeAPI](https://pokeapi.co/about)
  - Pokedex와 2020년 4월까지는 동일했지만, Generation 8 데이터가 추가됨.
  - [Python Wrapper for PokeAPI](https://github.com/PokeAPI/pokepy)

### GAN examples

- [Generating Pokemon with StyleGAN](https://www.youtube.com/watch?v=YM7NIwvsWcs) | [Code](https://colab.research.google.com/github/derekphilipau/machinelearningforartists/blob/main/stylegan2_ada_pytorch_pokemon.ipynb#scrollTo=R7JvPMLWy95f)
- [Generating Pokemon with AEGAN](https://github.com/ConorLazarou/PokeGAN)
- [Generating Pokemon with DCGAN](https://github.com/patrickbrightly/PokeGAN)
