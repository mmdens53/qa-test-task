# Анализ логики функции checkAccess

```js
function checkAccess(age, hasTicket, invited) {
  if (age < 18) {
    return "Доступ запрещен";
  }

  if (hasTicket == false && invited == false) {
    return "Нет билета или приглашения";
  }

  if (hasTicket == true || invited == true) {
    return "Доступ разрешен";
  }
}
