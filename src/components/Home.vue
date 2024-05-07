<template>
<Page>
    <ActionBar>
        <Label text="Home"/>
    </ActionBar>

    <GridLayout rows="auto, auto, auto" columns="*, *">
        <!-- Заголовок -->
        <Label class="info" row="0" colSpan="2">
            <FormattedString>
                <Span class="fas" text.decode="&#xf135; "/>
                <Span :text="message"/>
            </FormattedString>
        </Label>

        <!-- Поля ввода аккаунта -->
        <TextField hint="Введите имя пользователя" row="1" colSpan="2" v-model="username"/>
        <TextField hint="Введите пароль" row="2" colSpan="2" secure="true" v-model="password"/>

        <!-- Надпись "Нет аккаунта?" -->
        <Label text="Нет аккаунта?" row="3" col="0" horizontalAlignment="center"/>

        <!-- Кнопка "Регистрация" -->
        <Button text="Регистрация" row="3" col="1" @tap="register" horizontalAlignment="center"/>
    </GridLayout>
</Page>
</template>

<script>
export default {
data() {
  return {
    username: '',
    password: ''
  };
},
computed: {
  message() {
    return "Blank {N}-Vue app";
  }
},
methods: {
  register() {
    // Логика для обработки нажатия на кнопку "Регистрация"
    console.log('Регистрация нового аккаунта');
  }
}
};
</script>

<style scoped lang="scss">
@import '@nativescript/theme/scss/variables/blue';

// Custom styles
.fas {
    @include colorize($color: accent);
}

.info {
    font-size: 20;
    horizontal-align: center;
    vertical-align: center;
}
</style>
