---
marp: true
theme: uncover
class:
  - lead
paginate: true
---

# **Лабораторная работа №4**
## Продвинутое использование Git: Git-flow и Conventional Commits

**Выполнила:** Силантьева А.З.  
**Группа:** НКАбд-05-25  
**Дата:** 05 марта 2026

---

## **Цели работы**

- Освоить работу с git-flow на macOS
- Настроить conventional commits с помощью commitizen
- Научиться генерировать CHANGELOG через standard-changelog
- Создать два релиза (1.0.0 и 1.2.3) с автоматическим тегированием
- Опубликовать релизы на GitHub через CLI

---

## **Подготовка и установка ПО**

- **Git** – обновление до последней версии
- **git-flow** – `brew install git-flow`
- **Node.js и pnpm** – `brew install node`, `pnpm setup`
- **standard-changelog** – `pnpm add -g standard-changelog`
- **GitHub CLI (gh)** – `brew install gh`, затем `gh auth login`

---

## **Создание репозитория и первый коммит**

```bash
mkdir git-extended
cd git-extended
git init
echo "# git-extended" > README.md
git add README.md
git commit -m "first commit"
```
---
Связываем с удалённым репозиторием на GitHub:
git remote add origin git@github.com:<username>/git-extended.git

*git branch -M master
git push -u origin master*

---

Далее я настраивала conventional commits и инициализировала npm-пакета. 


### **pnpm init**

---

Редактировала package.json, добавляла секцию config для commitizen через git cz

---

## **Инициализация git-flow** и создание первого релиза (1.0.0)

![w:800](<../../Desktop/4 лаба/скрины/Снимок экрана 2026-03-05 в 17.18.32.png>)

---
## **Создание второго релиза (1.2.3)**
git flow release start 1.2.3
standard-changelog
git add package.json CHANGELOG.md
git commit -m "chore(site): update changelog and version"
git flow release finish 1.2.3
git push --all
gh release create v1.2.3 -F CHANGELOG.md

---
## **Результаты работы**
1) Освоена работа с git-flow на macOS
2) Настроены conventional commits с commitizen
3) Сгенерирован CHANGELOG с помощью standard-changelog
4) Созданы два релиза (1.0.0 и 1.2.3) с автоматическим тегированием
5) Релизы опубликованы на GitHub через CLI
 --- 
## **Вывод**

В ходе лабораторной работы я получила практические навыки использования продвинутых возможностей Git: модели ветвления Git-flow, семантического версионирования, conventional commits и автоматической генерации журнала изменений. Эти инструменты позволяют организовать профессиональный процесс разработки и поддержки программных проектов.

---

## **Cпасибо за внимание!**