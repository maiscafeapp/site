---
title: Quem Somos
description: Visão geral da empresa Mais Café
hide:
  - navigation
  - toc
  - author
  - revision_date
  - creation_date
---
--8<-- "includes/abbreviations.md"

<style type="text/css">
.rb-container {
  margin: auto;
  display: block;
  position: relative;
}

.rb-container ul.rb {
  padding: 0;
  display: inline-block;
}

.rb-container ul.rb li {
  list-style: none;
  margin: auto;
  min-height: 50px;
  border-left: 1px dashed var(--md-primary-fg-color);
  padding: 0 0 30px 20px;
  position: relative;
}

.rb-container ul.rb li:last-child {
  border-left: 0;
  padding-bottom: 0;
}

.rb-container ul.rb li::before {
  position: absolute;
  left: -11px;
  content: " ";
  border: 8px solid var(--md-primary-fg-color);
  border-radius: 500%;
  background: var(--md-primary-bg-color);
  height: 20px;
  width: 20px;
  transition: all 500ms ease-in-out;
}

.rb-container ul.rb li:hover::before {
  border-color: var(--md-accent-fg-color);
  transition: all 1000ms ease-in-out;
}

ul.rb li .timestamp {
  color: #50d890;
  position: relative;
  font-size: 13px;
}

ul.rb li:hover .timestamp {
  color: var(--md-accent-fg-color);
  transition: all 1000ms ease-in-out;
}
.item-description {
  display: none;
}
ul.rb li:hover .item-description {
  display: block;
  animation: fade-in 1s;
}
ul.rb li:not(:hover) .item-description.did-fade-in {
  display: block;
  animation: fade-out 1s;
}
@keyframes fade-in {
  from {
    opacity: 0;
  }
  to {
    opacity: .75;
  }
}

@keyframes fade-out {
  from {
    opacity: .75;
  }
  to {
    opacity: 0;
  }
}
.item-title::before {
  content:url('data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" fill="rgb(29,190,96)" viewBox="0 0 24 24"%3E%3Cpath d="M20 2H4c-1.11 0-2 .89-2 2v16c0 1.11.89 2 2 2h16c1.11 0 2-.89 2-2V4c0-1.11-.89-2-2-2m-9 2c2.21 0 4 1.79 4 4 0 1.5-.8 2.77-2 3.46v-1.22c.61-.55 1-1.35 1-2.24 0-1.66-1.34-3-3-3S8 6.34 8 8c0 .89.39 1.69 1 2.24v1.22C7.8 10.77 7 9.5 7 8c0-2.21 1.79-4 4-4m7 14.5c-.03.82-.68 1.47-1.5 1.5H11c-.38 0-.74-.15-1-.43l-4-4.2.74-.77c.19-.21.46-.32.76-.32h.2L10 16V8c0-.55.45-1 1-1s1 .45 1 1v4.47l1.21.13 3.94 2.19c.53.24.85.77.85 1.35v2.36z"/%3E%3C/svg%3E');
  margin: 0 8px 0 0px;
  vertical-align: middle;
  opacity: 0.65;
  display: inline-block;
  width: 19px;
  height: 19px;
}

.md-container .md-main .md-content__inner {
  margin: 0;
}
.md-container .md-main .md-content__inner .section-content-inner {
  margin: 0px .8rem 0;
  padding: 50px 0px;
  max-width: 61rem;
  margin-left: auto;
  margin-right: auto;
}
.md-container .md-main .md-content__inner .md-source-date {
  margin: 0 .8rem 0;
}
.md-container .md-main .md-content__inner hr {
  margin: 0 .8rem 0;
}

.md-container .md-main .md-content__inner section .row {
  margin-right: -.9375rem;
  margin-left: -.9375rem;
  align-items: center;
  display: flex;
  flex-flow: row wrap;
  width: 100%;
}
.md-container .md-main .md-content__inner section .col {
  padding: 0 2rem;
  width: 50%;
  flex: 0 0 auto;
  min-height: 0;
  min-width: 0;
}

.haze {
  background-color: var(--md-accent-fg-color--transparent);
}

.md-container .md-main .md-grid {
  max-width: unset;
}
.md-container .md-main .md-content__inner section .section-content-inner h1 {
  padding: 0 2rem;
  font-weight: bold;
  color: var(--md-primary-fg-color);
}
@media (max-width: 770px) {
  .md-container .md-main .md-content__inner section .row {
    flex-direction: column;
  }
  .md-container .md-main .md-content__inner section .reverse {
    flex-direction: column-reverse;
  }
  .md-container .md-main .md-content__inner section .col {
    width: unset;
  }
}
@media (min-width: 770px) {
  .md-container .md-main .md-content__inner section:not(.haze) .col {
    margin-top: -50px;
  }
}
.md-footer nav.md-footer__inner {
  display: none;
}
</style>

<section>
  <div class="rb-container section-content-inner">
    <h1>O Início de Tudo</h1>
    <div class="row">
      <div class="col">
        <img style="padding:5%;"  src="../assets/images/undraw_next_tasks_iubr.svg">
      </div>
      <div class="col">
        <ul class="rb">
          <li class="rb-item" ng-repeat="itembx">
            <div class="timestamp">
              <strong>2010</strong> - O Problema
            </div>
            <div class="item-title">Começamos a controlar a colheita de café da nossa propriedade pela planilha do Excel
            </div>
            <small class="item-description">
              Ajudou muito a controlar a colheita, mas com o tempo trouxe várias dores de cabeça, além de ser limitado.
            </small>
          </li>
          <li class="rb-item" ng-repeat="itembx">
            <div class="timestamp">
              <strong>2019</strong> - A Ideia
            </div>
            <div class="item-title">Início do desenvolvimento do aplicativo</div>
            <small class="item-description">
              9 anos após <a href="./equipe/">Erli</a> sair da roça e trabalhar com desenvolvimento de software, ele
              inicia o desenvolvimento do aplicativo para ajudar seu irmão na colheita do café.
            </small>
          </li>
          <li class="rb-item" ng-repeat="itembx">
            <div class="timestamp">
              <strong>2020</strong> - A Solução
            </div>
            <div class="item-title">Utilização do aplicativo para controle da colheita</div>
            <small class="item-description">
              Irmão do <a href="./equipe/">Erli</a> passa a utilizar o aplicativo.<br>
              Mais de 100 pessoas instalam o aplicativo, isso sem nenhuma divulgação ou propaganda.
            </small>
          </li>
          <li class="rb-item" ng-repeat="itembx">
            <div class="timestamp">
              <strong>2021</strong> - Nascimento do Mais Café
            </div>
            <div class="item-title">Estruturamos todo o aplicativo e o negócio</div>
            <small class="item-description">
              <dl>
                <dt>O Aplicativo</dt>
                <dd>
                  - Reescrevemos todo o aplicativo do zero para permitir crescer.<br>
                  - Criamos mais de 10 cadastros no aplicativo para servir como base para o cálculo custo de
                  produção.<br>
                  - Iniciamos a documentação de todo aplicativo.<br>
                </dd>
                <dt>O Negócio</dt>
                <dd>
                  - Evoluímos a ideia do aplicativo para tratar o Mais Café como uma empresa.<br>
                  - Foi montado um time, não está somente na mão de uma pessoa.<br>
                  - Definimos a cultura da empresa.<br>
                  - Melhoramos a cara do negócio, criamos vídeos institucional, website, etc.<br>
                </dd>
              </dl>
            </small>
          </li>
          <li class="rb-item" ng-repeat="itembx">
            <div class="timestamp">
              <strong>2022</strong> - Expansão do Produto
            </div>
            <div class="item-title">Foco no desenvolvimento do aplicativo</div>
            <small class="item-description">
              <p>
              Em 2022 o foco da equipe é no desenvolvimento do aplicativo, vamos focar nesse ano em melhorar o processo de colheita, <a href="./recursos/#planejamento-para-2022">saiba mais</a>.
              </p>
            </small>
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>

<section class="haze">
  <div class="section-content-inner">
    <h1>Nosso Produto</h1>
    <div class="row reverse">
      <div class="col">
        <p>O aplicativo pode ser comparado a uma lavoura de 2 a 3 anos, já compensa colher o café, mas a lavoura não está no auge de sua produção.</p>
        <p>Assim é o aplicativo, não temos todos os recursos disponíveis, mas acreditamos que já pode te ajudar.</p>
        Recursos úteis:
        <ul>
          <li>Registrar no mapa a localização dos talhões e medir os hectares da área.</li>
          <li>Registrar a colheita do café, separando para cada talhão e apanhador.</li>
          <li>Registrar a venda do café beneficiado.</li>
          <li>Lançar as doenças, pragas e anotações direto pelo mapa.</li>
          <li>Suporte para várias propriedades.</li>
        </ul>
      </div>
      <div class="col">
        <img src="../assets/images/illustration.png">
      </div>
    </div>
  </div>
</section>

<section>
  <div class="section-content-inner">
    <h1>Nossos Valores</h1>
    <div class="row">
      <div class="col">
        <img src="../assets/images/undraw_Career_development_re_sv91.svg">
      </div>
      <div class="col">
        <small>
          <ul>
            <li>Agir com integridade e dentro dos mais elevados padrões éticos não é negociável. </li>
            <li>Fazemos o que é certo e sempre cumprimos nossas promessas.</li>
            <li>Transparência em tudo que fazemos e com todos.</li>
            <li>Confiamos uns nos outros e trabalhamos juntos para fazer o trabalho, a melhor ideia vence.</li>
            <li>Atrair e reter talentos da mais alta qualidade e desenvolvê-los para que se tornem melhores do que nós.</li>
            <li>Tomamos decisões e agimos como donos do negócio, pensamos a longo prazo e não tomamos atalhos, para construir uma empresa sustentável.</li>
            <li>Acreditamos que todos podem ser líderes e que a verdadeira liderança é conquistada por meio de nossas ações, não com nossos títulos.</li>
            <li>Reconhecemos, recompensamos e celebramos o desempenho excepcional.</li>
            <li>Acreditamos que construir uma sociedade mais justa é possível quando pessoas incríveis estão dispostas a transformar vidas.</li>
            <li>Retribuir nosso crescimento com a sociedade é um dever.</li>
            <li>Consideramos o erro como parte do processo de aprendizagem, acreditamos que toda solução simples nasce de um experimento.</li>
          </ul>
        </small>
      </div>
    </div>
  </div>
</section>

<section class="haze">
  <div class="section-content-inner">
    <h1>Nossa Missão</h1>
    <div class="row reverse">
      <div class="col">
        <h2 style="color:var(--md-primary-fg-color);font-weight:bold;margin-top:0;padding-top:0;">Tornar a Tecnologia Acessível aos Cafeicultores</h2>
        <h3>
          Nossa missão vai além de criar soluções tecnológicas, é tornar acessível aos pequenos e médios cafeicultores o que há de melhor da tecnologia.<br>
        </h3>
        <p>
          Saiba mais em <a href="./objetivos/">objetivos</a>.
        </p>
      </div>
      <div class="col">
        <img src="../assets/images/undraw_product_iteration_kjok.svg">
      </div>
    </div>
  </div>
</section>

<section>
  <div class="section-content-inner">
    <h1>Nossos Investidores</h1>
    <div class="row">
      <div class="col">
        <img style="padding:20%;" src="../assets/images/undraw_personal_finance_tqcd.svg">
      </div>
      <div class="col">
        <h3>
          <p>Não temos nenhum investidor, enxugamos ao máximo para gerar o mínimo possível de gastos.</p>
          <p>Hoje não temos nenhuma receita, todos colaborares tem outro trabalho para se manter financeiramente.</p>
          <p>Todos os gastos são pagos pelo <a href="./equipe/">Erli</a>, mas estamos montando uma <a href="./preco/">proposta de cobrança</a> para os novos recursos que seja bom para todos.</p>
        </h3>
      </div>
    </div>
  </div>
</section>

<section class="haze">
  <div class="section-content-inner">
    <h1>Nosso Diferencial</h1>
    <div class="row reverse">
      <div class="col">
        <p>Somos uma equipe apaixonados pelo o que fazemos, cheio de ideias e vontade de fazer a diferença. Parte de nós nasceu e cresceu em meio a cafeicultura e conhece de perto o dia a dia do campo.</p>
        <p>Nosso diferencial:</p>
        <ul>
          <li>Entre em contato diretamente com quem faz acontecer.</li>
          <li>Integrantes da equipe tem mais de 8 anos em desenvolvimento de sistemas para grandes empresas, sabendo os prós e contras de cada detalhe do desenvolvimento.</li>
          <li>Vamos além de te oferecer um produto, queremos atender sua necessidade, até se para isso for necessário indicar um concorrente nosso.</li>  
        </ul>
      </div>
      <div class="col">
        <p>
          <img src="../assets/images/undraw_In_progress_re_m1l6.svg">
        </p>
      </div>
    </div>
  </div>
</section>
