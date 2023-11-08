# Zip Code challenge

A feladat célja azt megoldani, hogyha a felhasználó a ZipCode input mezőbe karaktereket ír,
vagy beilleszt, akkor az alkalmazásnak be kell hívnia egy végpontra, amely visszaadja az irányítószámhoz
tartozó várost / települést és ezt az értéket a City input mezőbe betölti. A végpont több találatot is visszaadhat, az
egyszerűség kedvéért elég csak az első találatot visszaadni.
Pl.: 3300 -> Eger

A következő végpontot célszerű használni:

```GET https://testa.free.beeceptor.com/zips/3000.json```

Bővebb információ itt: https://hur.webmania.cc/

A következő kis package hasznos lesz a HTTP kérések indításában:
- [Axios](https://axios-http.com/docs/intro)

Fontos lehet a Vue dokumentáció ezen része:
- [Event handling](https://vuejs.org/guide/essentials/event-handling.html)

Célszerű használni az input mező változás eseményéhez debounce-t, hogy késleltetve hívjon be a végpontra:
- [Vue Use](https://vueuse.org/)
- [Vue Use - Debounce](https://vueuse.org/shared/useDebounceFn/)

Az alkalmazás működő verzióban megtalálható ezen az URL-en:
https://vue-edu-zip-code-solution.vercel.app/

A projekt elő van készítve.
Először ```npm install``` majd ```npm run dev``` és már megy is!

