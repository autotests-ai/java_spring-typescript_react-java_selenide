# java_spring-typescript_react-java_selenide

Один стек, без матрицы других языков. Клонируй и запускай локально.

```bash
git clone https://github.com/autotests-ai/java_spring-typescript_react-java_selenide.git
cd java_spring-typescript_react-java_selenide
docker compose up -d --build
```

| Role | Folder |
|------|--------|
| Backend | `backend-java-spring/` |
| Frontend | `frontend-typescript-react/` (`vendor/` — запечённый design-system runtime) |
| Tests | `tests-java-gradle-junit5-allure3-selenide/` |

```bash
curl -sf http://localhost:8800/api/health
# UI same-origin (SPA + /api): http://localhost:9821/
# UI container only:          http://localhost:9811/
```

Tests (gateway already up):

```bash
cd tests-java-gradle-junit5-allure3-selenide
./gradlew testApi -Denv=multistack_ci -DallureReportMode=none
```

Maintainers: refresh from the live etalon in the zero-design-system monorepo:

```bash
./generators/render/render.sh --preset singlestack
```
