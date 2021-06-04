# Lotto_site
: Ruby on Rails 이용해서 간단한 "로또 번호 추천 사이트" 만들기

개발환경 : 구름 IDE

![image](https://user-images.githubusercontent.com/63999784/120757648-cac41800-c54b-11eb-9bba-3b288345f72c.png)


### /app/controllers/lotto_controller.rb

```
class LottoController < ApplicationController
	def index
		@byunsu = [*1..45]
		@lotto = @byunsu.sample(6).sort
	end
end
```

### /app/views/lotto/index.html.erb
```
<h1>
	로또 번호 추천
</h1>
<p>
	<span class="ball_645 lrg ball1"><%=@lotto[0]%></span>
	<span class="ball_645 lrg ball2"><%=@lotto[1]%></span>
	<span class="ball_645 lrg ball3"><%=@lotto[2]%></span>
	<span class="ball_645 lrg ball3"><%=@lotto[3]%></span>
	<span class="ball_645 lrg ball3"><%=@lotto[4]%></span>
	<span class="ball_645 lrg ball4"><%=@lotto[5]%></span>
</p>
```

### /config/routes.rb

```
Rails.application.routes.draw do
  # For details on the DSL available within this file, see https://guides.rubyonrails.org/routing.html
	get '/go', to: 'lotto#index'
end
```
