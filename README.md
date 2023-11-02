# Zip Code challenge

A feladat célja azt megoldani, hogyha a felhasználó a ZipCode input mezőbe karaktereket ír,
vagy beilleszt, akkor az alkalmazásnak be kell hívnia egy végpontra, amely visszaadja az irányítószámhoz
tartozó várost / települést és ezt az értéket a City input mezőbe betölti. A végpont több találatot is visszaadhat, az
egyszerűség kedvéért elég csak az első találatot visszaadni.
Pl.: 3300 -> Eger

![Képernyőfotó 2023-11-02 - 17.37.46.png](..%2F..%2F..%2F..%2F..%2F..%2Fvar%2Ffolders%2F_b%2F6gpdnfbx12ggxzspl4prrbtr0000gp%2FT%2FTemporaryItems%2FNSIRD_screencaptureui_2j4lPd%2FK%C3%A9perny%C5%91fot%C3%B3%202023-11-02%20-%2017.37.46.png)

A következő végpontot célszerű használni:

```GET https://hur.webmania.cc/zips/3300.json```

Bővebb információ itt: https://hur.webmania.cc/

A projekt elő van készítve.
Először ```npm install``` majd ```npm run dev``` és már megy is!

