---
layout: publicar
title: Web Vitals
description: Métricas essenciais para um site saudável
hero: image/admin/BHaoqqR73jDWe6FL2kfw.png
authors:
  - philipwalton
date: 30/04/2020
updated: '2020-07-21'
tags:
  - Métricas
  - atuação
  - web-vitals
---

Otimizar a qualidade da experiência do usuário é a chave para o sucesso a longo prazo de qualquer site na web. Seja você proprietário de uma empresa, profissional de marketing ou desenvolvedor, o Web Vitals pode ajudá-lo a quantificar a experiência do seu site e identificar oportunidades de melhoria.

## Visão geral

O Web Vitals é uma iniciativa do Google para fornecer orientação unificada para sinais de qualidade essenciais para proporcionar uma ótima experiência do usuário na web.

O Google forneceu várias ferramentas ao longo dos anos para medir e relatar o desempenho. Alguns desenvolvedores são especialistas no uso dessas ferramentas, enquanto outros consideram difícil acompanhar a abundância de ferramentas e métricas.

Os proprietários de sites não devem ser gurus de desempenho para entender a qualidade da experiência que estão oferecendo a seus usuários. A iniciativa Web Vitals visa simplificar o cenário e ajudar os sites a se concentrarem nas métricas mais importantes, o **Core Web Vitals** .

## Pontos vitais principais da Web

As principais métricas da Web são o subconjunto das principais métricas da Web que se aplicam a todas as páginas da Web, devem ser medidas por todos os proprietários de sites e serão exibidas em todas as ferramentas do Google. Cada um dos Core Web Vitals representa uma faceta distinta da experiência do usuário, é mensurável [no campo](/user-centric-performance-metrics/#how-metrics-are-measured) e reflete a experiência do mundo real de um resultado crítico [centrado no usuário](/user-centric-performance-metrics/#how-metrics-are-measured) .

As métricas que compõem o Core Web Vitals [evoluirão](#evolving-web-vitals) com o tempo. O conjunto atual para 2020 se concentra em três aspectos da experiência do usuário — *carregamento* , *interatividade* e *estabilidade visual* — e inclui as seguintes métricas (e seus respectivos limites):

<div class="w-stack w-stack--center w-stack--md">
<img src="lcp_ux.svg" width="400px" height="350px" alt="Maiores recomendações de limite de exibição de conteúdo"><img src="fid_ux.svg" width="400px" height="350px" alt="Recomendações de limite do primeiro atraso de entrada"><img src="cls_ux.svg" width="400px" height="350px" alt="Recomendações de limite cumulativo de mudança de layout">
</div>

- **[Maior pintura de conteúdo (LCP)](/lcp/)** : mede o desempenho *de carregamento* . Para fornecer uma boa experiência ao usuário, o LCP deve ocorrer dentro de **2,5 segundos** após o início do carregamento da página.
- **[First Input Delay (FID)](/fid/)** : mede a *interatividade* . Para fornecer uma boa experiência ao usuário, as páginas devem ter um FID inferior a **100 milissegundos** .
- **[Deslocamento Cumulativo de Layout (CLS)](/cls/)** : mede *a estabilidade visual* . Para fornecer uma boa experiência ao usuário, as páginas devem manter um CLS inferior a **0,1.**

Para cada uma das métricas acima, para garantir que você esteja atingindo a meta recomendada para a maioria de seus usuários, um bom limite para medir é o **75º percentil** de carregamentos de página, segmentado em dispositivos móveis e computadores.

As ferramentas que avaliam a conformidade do Core Web Vitals devem considerar uma passagem de página se ela atender às metas recomendadas no percentil 75 para todas as três métricas acima.

{% Aside %} Para saber mais sobre a pesquisa e a metodologia por trás dessas recomendações, consulte: [Definindo os limites das métricas de principais métricas da Web](/defining-core-web-vitals-thresholds/) {% endAside %}

### Ferramentas para medir e relatar Core Web Vitals

O Google acredita que os Core Web Vitals são críticos para todas as experiências na web. Como resultado, está empenhada em trazer à tona essas métricas [em todas as suas ferramentas populares](/vitals-tools/) . As seções a seguir detalham quais ferramentas suportam o Core Web Vitals.

#### Ferramentas de campo para medir os Core Web Vitals

O[Relatório de experiência do usuário do Chrome](https://developers.google.com/web/tools/chrome-user-experience-report) coleta dados anônimos e reais de medição do usuário para cada Core Web Vital. Esses dados permitem que os proprietários de sites avaliem rapidamente seu desempenho, sem a necessidade de instrumentar análises manualmente em suas páginas, além de capacitar ferramentas como o [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) e o [relatório Core Web Vitals](https://support.google.com/webmasters/answer/9205520) do Search Console.

<div class="w-table-wrapper">
  <table>
    <tr>
      <td> </td>
      <td>LCP</td>
      <td>FID</td>
      <td>CLS</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/web/tools/chrome-user-experience-report">Relatório de experiência do usuário do Chrome</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://developers.google.com/speed/pagespeed/insights/">Insights de velocidade de página</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
    <tr>
      <td><a href="https://support.google.com/webmasters/answer/9205520">Search Console (relatório de principais métricas da Web)</a></td>
      <td>✔</td>
      <td>✔</td>
      <td>✔</td>
    </tr>
  </table>
</div>

{% Aside %} Para obter orientação sobre como usar essas ferramentas e qual ferramenta é adequada para seu caso de uso, consulte: [Introdução à medição de Web](/vitals-measurement-getting-started/) Vitals {% endAside %}

Os dados fornecidos pelo Relatório de experiência do usuário do Chrome oferecem uma maneira rápida de avaliar o desempenho dos sites, mas não fornecem a telemetria detalhada por exibição de página que geralmente é necessária para diagnosticar, monitorar e reagir rapidamente a regressões com precisão. Como resultado, recomendamos enfaticamente que os sites configurem seu próprio monitoramento de usuários reais.

#### Avalie as principais métricas da Web em JavaScript

Cada um dos Core Web Vitals pode ser medido em JavaScript usando APIs da web padrão.

A maneira mais fácil de medir todos os Core Web Vitals é usar a biblioteca JavaScript [web-vitals](https://github.com/GoogleChrome/web-vitals) , um pequeno invólucro pronto para produção em torno das APIs da Web subjacentes que mede cada métrica de uma maneira que corresponda com precisão a como elas são relatadas por todos os Ferramentas do Google listadas acima.

Com a biblioteca [web-vitals](https://github.com/GoogleChrome/web-vitals) , medir cada métrica é tão simples quanto chamar uma única função (consulte a documentação para [uso](https://github.com/GoogleChrome/web-vitals#usage) completo e detalhes da [API](https://github.com/GoogleChrome/web-vitals#api) ):

```js
import {getCLS, getFID, getLCP} from 'web-vitals';

function sendToAnalytics(metric) {
  const body = JSON.stringify(metric);
  // Use `navigator.sendBeacon()` if available, falling back to `fetch()`.
  (navigator.sendBeacon && navigator.sendBeacon('/analytics', body)) ||
      fetch('/analytics', {body, method: 'POST', keepalive: true});
}

getCLS(sendToAnalytics);
getFID(sendToAnalytics);
getLCP(sendToAnalytics);
```

Depois de configurar seu site para usar a biblioteca [web-vitals](https://github.com/GoogleChrome/web-vitals) para medir e enviar seus dados de Core Web Vitals para um endpoint analítico, a próxima etapa é agregar e relatar esses dados para ver se suas páginas estão atendendo aos limites recomendados para pelo menos 75% das visitas à página.

Embora alguns provedores de análise tenham suporte integrado para as métricas do Core Web Vitals, mesmo aqueles que não o fazem devem incluir recursos básicos de métrica personalizada que permitem medir o Core Web Vitals em sua ferramenta.

Um exemplo disso é o [Web Vitals Report](https://github.com/GoogleChromeLabs/web-vitals-report) , que permite que os proprietários de sites avaliem suas principais métricas da Web usando o Google Analytics. Para obter orientação sobre como medir os principais indicadores vitais da Web usando outras ferramentas de análise, consulte [as práticas recomendadas para medir os indicadores vitais da Web no campo](/vitals-field-measurement-best-practices/) .

Você também pode relatar cada um dos principais indicadores vitais da Web sem escrever nenhum código usando a [extensão Chrome Web Vitals](https://github.com/GoogleChrome/web-vitals-extension) . Essa extensão usa a biblioteca [web-vitals](https://github.com/GoogleChrome/web-vitals) para medir cada uma dessas métricas e exibi-las aos usuários enquanto eles navegam na web.

Essa extensão pode ser útil para entender o desempenho de seus próprios sites, dos sites de seus concorrentes e da Web em geral.

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>FID</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals">web-vitals</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://github.com/GoogleChrome/web-vitals-extension">Extensão Web Vitals</a></td>
        <td>✔</td>
        <td>✔</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

Como alternativa, os desenvolvedores que preferem medir essas métricas diretamente por meio das APIs da Web subjacentes podem consultar estes guias de métricas para obter detalhes de implementação:

- [Medir LCP em JavaScript](/lcp/#measure-lcp-in-javascript)
- [Medir FID em JavaScript](/fid/#measure-fid-in-javascript)
- [Medir CLS em JavaScript](/cls/#measure-cls-in-javascript)

{% Aside %} Para obter orientações adicionais sobre como medir essas métricas usando serviços de análise populares (ou suas próprias ferramentas de análise internas), consulte: [Práticas recomendadas para medir Web Vitals in the field](/vitals-field-measurement-best-practices/) {% endAside %}

#### Ferramentas de laboratório para medir os Core Web Vitals

Embora todos os Core Web Vitals sejam, antes de mais nada, métricas de campo, muitos deles também podem ser medidos em laboratório.

A medição de laboratório é a melhor maneira de testar o desempenho dos recursos durante o desenvolvimento — antes de serem liberados para os usuários. Também é a melhor maneira de capturar regressões de desempenho antes que elas aconteçam.

As seguintes ferramentas podem ser usadas para medir os Core Web Vitals em um ambiente de laboratório:

<div class="w-table-wrapper">
  <table>
    <thead>
      <tr>
        <th> </th>
        <th>LCP</th>
        <th>FID</th>
        <th>CLS</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td><a href="https://developers.google.com/web/tools/chrome-devtools">Chrome DevTools</a></td>
        <td>✔</td>
        <td>✘ (use <a href="/tbt/">TBT</a> em vez disso)</td>
        <td>✔</td>
      </tr>
      <tr>
        <td><a href="https://developers.google.com/web/tools/lighthouse">Farol</a></td>
        <td>✔</td>
        <td>✘ (use <a href="/tbt/">TBT</a> em vez disso)</td>
        <td>✔</td>
      </tr>
    </tbody>
  </table>
</div>

{% À parte %} Ferramentas como o Lighthouse, que carregam páginas em um ambiente simulado sem um usuário, não podem medir o FID (não há entrada do usuário). No entanto, a métrica Tempo Total de Bloqueio (TBT) é mensurável em laboratório e é um excelente proxy para o FID. As otimizações de desempenho que melhoram o TBT no laboratório devem melhorar o FID no campo (consulte as recomendações de desempenho abaixo). {% endAside %}

Embora a medição em laboratório seja uma parte essencial para proporcionar ótimas experiências, ela não substitui a medição em campo.

O desempenho de um site pode variar drasticamente de acordo com os recursos do dispositivo do usuário, suas condições de rede, quais outros processos podem estar sendo executados no dispositivo e como eles estão interagindo com a página. Na verdade, cada uma das métricas do Core Web Vitals pode ter sua pontuação afetada pela interação do usuário. Somente a medição de campo pode capturar com precisão a imagem completa.

### Recomendações para melhorar sua pontuação

Depois de medir os principais indicadores vitais da Web e identificar as áreas de melhoria, a próxima etapa é otimizar. Os guias a seguir oferecem recomendações específicas sobre como otimizar suas páginas para cada um dos Principais Pontos Vitais da Web:

- [Otimizar LCP](/optimize-lcp/)
- [Otimizar FID](/optimize-fid/)
- [Otimizar CLS](/optimize-cls/)

## Outras Web Vitals

Embora os principais indicadores vitais da Web sejam as métricas críticas para entender e oferecer uma ótima experiência ao usuário, também existem outras métricas vitais.

Esses outros Web Vitals geralmente servem como proxy ou métricas complementares para os principais Web Vitals, para ajudar a capturar uma parte maior da experiência ou para auxiliar no diagnóstico de um problema específico.

Por exemplo, as métricas [Time to First Byte (TTFB)](/time-to-first-byte/) e [First Contentful Paint (FCP)](/fcp/) são aspectos vitais da experiência de *carregamento* e são úteis para diagnosticar problemas com LCP ( [tempos de resposta lentos do servidor](/overloaded-server/) ou [recursos de bloqueio de renderização](/render-blocking-resources/) , respectivamente) .

Da mesma forma, métricas como [Total Blocking Time (TBT)](/tbt/) e [Time to Interactive (TTI)](/tti/) são métricas de laboratório vitais para detectar e diagnosticar possíveis problemas de *interatividade* que afetarão o FID. No entanto, eles não fazem parte do conjunto de Core Web Vitals porque não são mensuráveis em campo, nem refletem um resultado [centrado no usuário](/user-centric-performance-metrics/#how-metrics-are-measured) .

## Sinais vitais da Web em evolução

Web Vitals e Core Web Vitals representam os melhores sinais disponíveis que os desenvolvedores têm hoje para medir a qualidade da experiência na web, mas esses sinais não são perfeitos e futuras melhorias ou adições devem ser esperadas.

O **Core Web Vitals** é relevante para todas as páginas da web e apresentado em ferramentas relevantes do Google. As alterações nessas métricas terão um impacto de amplo alcance; como tal, os desenvolvedores devem esperar que as definições e os limites do Core Web Vitals sejam estáveis e que as atualizações tenham aviso prévio e uma cadência anual previsível.

Os outros Web Vitals geralmente são específicos do contexto ou da ferramenta e podem ser mais experimentais do que os principais Web Vitals. Como tal, suas definições e limites podem mudar com maior frequência.

Para todos os Web Vitals, as alterações serão claramente documentadas neste [CHANGELOG](http://bit.ly/chrome-speed-metrics-changelog) público.
