# Peruvian Football News Generator using Generative Models

The objective of this project is to create a generative text model that creates peruvian football news.

<img src="/objetive.png" height="350">

For this, web scraping was first performed using selenium in python to extract the football news from the newspaper 'Peru21'. The headline, subtitle and body of the news were extracted from 01/01/23 to 11/12/23.

<img src="/web-scraping.png" height="350">

With the data obtained, a text generative model (GRU) was trained using 100 epochs and fine-tuning was performed on 2 pre-trained models (GPT2-spanish & Llama-2-7b-alpaca-es).

<img src="/models.png" height="350">


## Results
### Llama-2-7b-alpaca-es:

```Python
generate("Universitario ganó la final:")
```

**Response:** "Universitario de Deportes se proclamó campeón de la Liga 1 Betsson 2023 tras imponerse por 1-0 a Sporting Cristal en la final disputada en el estadio Alejandro Villanueva, en Matute. El único tanto del encuentro lo anotó Yordi Vílchez a los 20 minutos del primer tiempo. Con este resultado, Universitario de Deportes se proclama campeón de la Liga 1 Betsson 2023. Sporting Cristal se quedó con el subcampeonato. Universitario de Deportes ganó la Liga 1 Betsson 2023"

```Python
generate("Universitario lo ganó al final del partido:")
```

**Response:** "Universitario lo ganó al final del partido. Universitario de Deportes le ganó 1-0 a Sporting Cristal en el estadio Monumental de Ate, en un duelo válido por la fecha 10 de la Liga 1 Betsson 2023. Con este resultado, los cremas suman 24 puntos en la tabla de posiciones y se ubican en el segundo lugar de la Liga 1 Betsson 2023. Sporting Cristal, por su parte, suma 21 unidades y se ubican en la tercera posición de la tabla de posiciones."

```Python
generate("El torneo Clausura se puso interesante:")
```

**Response:** "El Clausura de la Liga 1 Betsson 2023 se ha posicionado como uno de los torneos más emocionantes de la historia del fútbol peruano. Desde el inicio del campeonato, los clubes más poderosos de la Liga 1, como Universitario de Deportes, Sporting Cristal, Alianza Lima y Cienciano, se han mantenido en las primeras posiciones de la tabla acumulada de la Liga 1 Betsson 2023. Sin embargo, en la segunda mitad del Clausura, el torneo se ha posicionado como uno de los más emocionantes de la historia del fútbol"

### GPT2:
```Python
prompt = "<|startoftext|>" + "Universitario ganó la final:"
```

**Response:** Universitario ganó la final: hasta la fecha, los cremas han perdido la final de la liga 1 2023 ante Eibar por el título en el monumental de la victoria de los merengues sobre el juego más vistoso y emocionante hasta la fecha. universitario campeón 2024.

```Python
prompt = "<|startoftext|>" + "Universitario ganó y se pone primero en el torneo Clausura"
```

**Response:** Universitario ganó y se pone primero en el torneo Clausura: hasta que se niegue, será que el torneo clausura se disputará en el estadio monumental. válido por la fecha 18 de la segunda categoría del fútbol peruano. el gol de la victoria de universitario de deportes sobre alianza lima, correspondiente a la decimocuarta jornada. como se recuerda, un encuentro disputado por la fecha anterior, donde los cremas empataron 1 a 1, con un tanto del defensor de la crema, mónaco josé olaya. sin embargo, en el torneo clausura, los cremas empataron 1-1 con adt, en matute. para no perderle el ritmo al clausura, universitario de deportes recibirá al adt este domingo 10 de abril a las 0330 de la tarde en el estadio mansichenn

```Python
prompt = "<|startoftext|>" + "El torneo Clausura se puso interesante"
```

**1. Response:** El torneo Clausura se puso interesante con la presentación de Alianza Lima sacó un gran triunfo por 2-0 ante Unión Comercio en el estadio Alejandro Villanueva. los blanquiazules descontaron un par de minutos a un rival que intentó pero no pudo. luego del tanto de penal marcado por el argentino de la selección peruana, el partido se volvió loco y los hinchas locales salieron a respaldar al equipo. tras el encuentro, el entrenador uruguayo de la blanquirroja, julinho, se refirió al gol del triunfo y la reacción de su equipo. el equipo intentó siempre, pero no siempre gana. en el primer tiempo, el equipo visitante se hizo fuerte, pero no creó problemas. en el segundo tiempo, casi hizo el gol de la tranquilidad, solo lo intentaron en una ocasión y no lograron anotar. en el segundo tiempo, casi hizo el gol de la tranquilidad. en un contraataque, barreto anota el primer gol del 2-0 y todo fue emoción en el estadio. barreto mandó la tirolesa para los locales que fue todo un éxito. luego del tanto de barreto, el encuentro se puso emocionante y no se movería. hasta que en el final, barreto nuevamente dispara, pero esta vez al arco y se vuelve a gritar gol. barreto salva al equipo. ¡goooool!

**2. Response:** El torneo Clausura se puso interesante este miércoles con el partido entre universitario de deportes y alianza lima en el estadio monumental. Ambos clubes se repartieron los puntos de nueve partidos y ahora tendrán que enfrentarse en otro partido para no perderle el ritmo al líder del campeonato.

### GRU (Gated Recurrent Unit):

**Input:** ```Todo está listo para la final```

**Response:** Todo está listo para la final de la Liga 1, este emotivo corte audiovisual se ha convertido en un símbolo de la pasión que despierta el fútbol en el Perú y cómo puede unir a las personas en torno a algo más grande que el deporte en sí. Los aficionados de Alianza Lima y Universitario, así como todos los peruanos, se preparan para una final inolvidable, y este video es el preludio perfecto para el partido más emocionante del año.

**Input:** ```Universitario ganó la final:```

**Response:** La festeja de Universitario de Deportes a los 94 minutos del partido y generó la alegría no solo de sus hinchas, sino también del apostador más suertudo del domindo después de 10 años y ante su clásico rival, pero no solo eso, sino también por el jugoso premio que recibirá hoy en el Monumental. Los jugadores de Universitario de Deportes fueron ampayados bebiendo alcohol a altas horas de la madrugada, pero esto fue algo que el administrador crema, Jean Ferrari, minimizó y que, inclusive, deslizó que podría ser para desconcentrarlos de lo deportivo. Esa clase de situaciones ampays la señal de Liga 1 MAX y DirecTV Sports.


**Input:** ```Alianza apagó las luces del estadio```

**Response:** Alianza apagó las luces del estadio Alejandro Villanueva se apagaron poniendo en riesgo a todos los presentes ¿Acaso nunca nos vamos a respetar mutuamente?.


**Input:** ```Universitario se enfrenta a Sporting Cristal el domingo```

**Response:** Universitario se enfrenta a Sporting Cristal el domingo 16 de abril a las 0400 de la tarde en el estadio Alberto Gallardo por la fecha 4 del Torneo Clausura. Este encuentro será administrado por el árbitro Michael Espinoza en el campo y por el juez Jonathan Zamora interpretando todas las imágenes del partido desde la sala del VAR. La Liga 1 Max será la encargada de hacer llegar la señal del enfrentamiento entre Sporting Cristal y Carlos A. Mannucci a todos los peruanos por medio de los canales 11 y 610 de Bestcable y DirecTV, respectivamente o por la web oficial del torneo.