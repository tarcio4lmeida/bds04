## 📦 TESTES - TAREFA: DESAFIO03

### Desafio com Spring Validation & Security

![img.png](img.png)

## Anotations de testes

| Name                                    | Description                                                                                                                                      |
|-----------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `@SpringBootTest`                       | Carrega o contexto da aplicação (teste de integração)                                                                                            |
| `@SpringBootTest @AutoConfigureMockMvc` | Carrega o contexto da aplicação (teste de integração & web) Trata as requisições sem subir o servidor                                            |
| `@WebMvcTest(Classe.class)`             | Carrega o contexto, porém somente da camada web (teste de unidade: controlador)                                                                  |
| `@ExtendWith(SpringExtension.class)`    | Não carrega o contexto, mas permite usar os recursos do Spring com JUnit (teste de unidade: service/component)                                   |
| `@DataJpaTest`                          | Carrega somente os componentes relacionados ao Spring Data JPA. Cada teste é transacional e dá rollback ao final. (teste de unidade: repository) |

### Fixtures


| JUnit 5       | Objetivo                                                      |
|---------------|---------------------------------------------------------------|
| `@BeforeAll`  | Preparação antes de todos testes da classe (método estático)  |
| `@AfterAll`   | Preparação depois de todos testes da classe (método estático) |
| `@BeforeEach` | Preparação antes de cada teste da classe                      |
| `@AfterEach`  | Preparação depois de cada teste da classe                     |

### Mockito vs @MockBean

| JUnit 5                                                               | Objetivo                                                                                                                           |
|-----------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| `@Mock private MyComp myComp ou myComp = Mockito.mock(MyComp.class);` | Usar quando a classe de teste não carrega o contexto da aplicação. É mais rápido e enxuto. @ExtendWith                             |
| `@MockBean private MyComp myComp;`                                    | Usar quando a classe de teste carrega o contexto da aplicação e precisa mockar algum bean do sistema. @WebMvcTest @SpringBootTest  |
