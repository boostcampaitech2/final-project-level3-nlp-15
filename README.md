# Pokemon-DALLE

DALL-E model adapted to Pokemon image generation domain.

### 목표

- Descriptive Text → Image Generation Model adapted to Pokemon Domain.
- 3~4줄의 내용 → 64 x 64 pixel 혹은 225 x 225 pixel
- **프로젝트 막바지에 BART → VQGAN으로 생성한 포켓몬 이미지들을 NFT화하고 등록하기**

---

### 데이터셋

```
지금의 포켓몬스터의 디자인이 나오기까지 디자인을 담당하는 스기모리 켄이 약 300여가지의 스케치를 그렸다. 그 후 사내 인기투표까지 하면서 다시 그려낸 150여마리의 포켓몬을 엄선하게 되었다. 포켓몬의 수는 시리즈가 나올 때마다 100마리, 135마리, 107마리, 156마리, 72마리, 86마리, 2마리[12], 82마리, 7마리[13]가 추가되어 8세대까지 총 898마리가 되었다.
```

- [Pokedex 898 마리](https://github.com/veekun/pokedex) | [데이터 예시: PokeSprite](https://msikma.github.io/pokesprite/overview/dex-gen8.html)
  - Pokemon Shapes: wings, squiggle, fish...
  - 한국어도 있음.
  - MIT License만 지키면 맘대로 사용 가능함.
  - [Python Wrapper for Pokedex](https://github.com/PokeDevs/pokedex.py.git)
- [PokeAPI](https://pokeapi.co/about)
  - Pokedex와 2020년 4월까지는 동일했지만, Generation 8 데이터가 추가됨.
  - [Python Wrapper for PokeAPI](https://github.com/PokeAPI/pokepy)

---

### GAN examples

- [Generating Pokemon with StyleGAN](https://www.youtube.com/watch?v=YM7NIwvsWcs) | [Code](https://colab.research.google.com/github/derekphilipau/machinelearningforartists/blob/main/stylegan2_ada_pytorch_pokemon.ipynb#scrollTo=R7JvPMLWy95f)
- [Generating Pokemon with AEGAN](https://github.com/ConorLazarou/PokeGAN)
- [Generating Pokemon with DCGAN](https://github.com/patrickbrightly/PokeGAN)

---

### [👉 Notion Work Space](https://www.notion.so/Pokemon-Dall-E-de132b5ce0df4456af309cf336f77bec)

### 제안 배경 - 차별점

- 컨셉을 기반으로 몬스터 디자인을 새로 만들어야 하는 게임 회사들에게 어필하기 좋은 프로젝트이다. (ex: 닌텐도의 포켓몬, 넥슨의 메이플스토리, 블리자드의 디아블로, NC의 리니지 등)
- 현재 오픈되어 있는 Mini-DALLE 같은 경우는 포켓몬 생성에 있어서는 취약하다. 따라서 Pokemon-DALLE가 다른 DALLE들과는 차별점을 가질 수 있다고 생각한다.
- 최소한 Multimodal을 시도해봤다는 경험이 다른 회사들에게도 어필이 될 거라고 생각한다. Domain Specific하게 DALLE를 만들어 보는 경험도 다른 개발자들에게 유의미하게 다가올 것 같다.
- 포켓몬은 옛날 컨텐츠임에도 불구하고 Pokemon Go 등의 새로운 형식을 좋아하는 해외 팬덤층이 두텁다. 따라서 해당 프로젝트를 pokemon reddit 등 커뮤니티에 알리면 꽤나 많은 유저들을 유입시키거나, 혹은 유명세를 탈 수 있다고 생각한다.
- 데이터셋을 새롭게 모아야 프로젝트 결과가 차별화된다. 그렇지만 정형화된 데이터셋을 새로 모으기는 힘든데, 포켓몬은 오픈소스 SQL 데이터가 있다. 위키피디아 데이터셋 정제 및 훈련하는 것도 시중에 자료가 많이 있다.

### 제안배경 - 현실성

- OpenAI의 DALL-E처럼 넓은 domain의 multimodal은 32GB GPU로 하기에는 한계가 분명히 있다. 이를 Pokemon domain으로 좁힌다면, 주어진 컴퓨팅 리소스로 실험을 해볼 수 있다고 생각한다.
- 포켓몬 위키피디아 데이터가 각 포켓몬의 type을 분류해놓았기 때문에, Conditional Generation이 가능하기도 하다. 따라서 description을 직접 서술형으로 입력하는 대신에 유저에게 드롭다운으로 객관식으로 선택할 수 있게끔 할 수도 있다. (ex: 전기속성, 모양새, 크기 등)
- Pokemon 게임은 역사가 오래됐기 때문에, 유저들은 저화질 포켓몬들에 익숙하다. 포켓몬 이미지들은 64 x 64 pixel, 96 x 96 pixel 정도로 경량 이미지들이다. 따라서 32GB GPU를 이용하여 훈련하기에도 적합하다.
- 시중에 사용할 수 있는 Pokemon 데이터셋이 많고, 성공한 것으로 보이는 GAN 프로젝트들이 많기 때문에 학습에도 용이하다고 생각한다.
- 포켓몬의 "진화" 개념은 GAN의 Train epoch에 따른 변화로 표현할 수도 있다.
- Pokemon-DALLE가 만든 포켓몬을 NFT화시키면 상징성과 성취감이 있을 거라고 생각한다. 내가 만든 포켓몬을 소장하고 싶은 욕구는 누구나 갖고 있을 거라고 생각하기 때문이다.
