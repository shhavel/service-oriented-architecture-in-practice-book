Прадмова
========

## <a name="http-apis"></a>HTTP APIs

У свеце інфармацыйных тэхналогій усё круціцца вакол ... інфармацыі. І Інтэрнэт з'яўляецца вельмі выдатным спосабам распаўсюджвання інфармацыі. Здольнасць карыстальнікаў атрымліваць доступ да інфармацыі мае значэнне.

Разгледзім невялікі прыклад. Выкажам здагадку, што ў вас ёсць сайт і вы заробатываете змяшчаючы рэкламу на старонках сайта. Чым больш кантэнту (або даных, або інфармацыі) у вас ёсць і чым больш высокага ён якасці (чым цікавей ён для карыстальнікаў), тым больш грошай вы зарабляеце. Калі ваш сайт з'яўляецца статычным (заўсёды тое ж самае колькасць тых жа старонак) вы не маеце шмат варыянтаў, каб павялічыць прыбытак. Вы можаце наняць мадэратараў (ці самі быць мадэратарам) для таго, каб ствараць новае змесціва. Праца мадэратараў павялічвае колькасць кантэнту лінейна.

Вы можаце захацець павялічыць хуткасць стварэння кантэнту. І вы вырашыце адкрыць доступ для карыстальнікаў. Калі карыстальнікі будуць матываваныя для дадання новага кантэнту на вашым сайце, колькасць кантэнту будзе расці ў геаметрычнай прагрэсіі, таму што, чым больш кантэнту ў вас ёсць - тым больш карыстальнікаў у вас будзе, і чым больш карыстальнікаў у вас ёсць - тым больш новага кантэнту яны ствараюць.

![](../static/images/content_vs_time_ru.png)

І яшчэ! Цяпер вы можаце ўзаемадзейнічаць з іншымі сайтамі або службамі, каб дазволіць карыстальнікам іншых вэб-сайтаў атрымаць доступ да змесціва. Чым больш просты і зручны спосаб Вы знойдзеце - тым больш паспяховым апынецца ваш вэб сайт. Цяжка сабе ўявіць ...

Гэта не адзіная вобласць прымянення HTTP API. Ёсць праекты, якія ўнутрана складаюцца з маленькіх вэб-сэрвісаў, якія ўзаемадзейнічаюць адзін з адным з дапамогай API. Такога роду праект можна таксама назваць API. Архітэктура такога праекта называецца сэрвіс-арыентаванай архітэктурай, якой прысвечана гэта кніга.

## <a name="rpc-vs-rest"></a>RPC і REST

Так што, калі вам трэба падаць доступ да вашаму з дадаткам для некаторых іншых прыкладанняў, якія могуць падтрымлівацца іншымі распрацоўшчыкамі і могуць быць напісаны на розных мовах праграмавання, то Вы павінны даць HTTP API. У цэлым гэта канчатковы спіс аддаленых выклікаў (або метадаў, або працэдур) са сваёй спецыфікацыяй.

Пажадана выкарыстоўваць некаторы добра вядомы або інтуітыўна зразумелы інтэрфейс. Адным з варыянтаў з'яўляецца выкарыстанне XML-RPC (Remote Procedure Call), ён выкарыстоўвае XML для кадавання паведамленняў - метады і дадзеныя ў фармаце XML. XML-RPC - гэта пэўны пратакол для метаду і дадзеных, якія перадаюцца па HTTP.

HTTP таксама з'яўляецца пратаколам. `REST` (скар. Ад англ. Representational State Transfer - перадача стану прадстаўлення) цалкам належыць на HTTP. URL выкарыстоўваецца для вызначэння тыпу рэсурсу або унікальнай запісу рэсурсу. Метад HTTP (напрыклад, `POST`, `GET`, `PUT`, `DELETE`) выкарыстоўваецца для вызначэння метаду (стварэнне, чытанне, абнаўленне, выдаленне). Гэтага набору атамных метадаў павінна быць дастаткова для таго, каб выканаць любую патрэбную аперацыю. У параўнанні з REST XML-RPC, як канверт з дадзенымі (Верхні ўзровень XML), размешчаных у іншай канверт (HTTP).

У гэтай кнізе мы будзем прытрымлівацца `REST` канвенцый.

## <a name="technologies"></a>Тэхналогіі

У гэтай кнізе мы не будзем параўноўваць розныя тэхналогіі, якія могуць быць выкарыстаны для стварэння вэб-сэрвісаў.

Мы засяродзімся на агульнай архітэктуры вэб-сэрвісу. Мы будзем выкарыстоўваць мову праграмавання Ruby. Ruby - лаканічны і зразумелая мова праграмавання. Таксама мы будзем выкарыстоўваць `sinatra` фреймворк і звязаныя з ім` ruby` гемы.

Каб пачаць чытаць кнігу, вы павінны мець `ruby` (1.9 або больш новы), і RubyGems усталяванымі ў вашай сістэме.

Фармат серыялізацыі дадзеных - у асноўным JSON.

## <a name="technologies"></a>Прыклады кода

Вы можаце знайсці прыклады кода, якія выкарыстоўваюцца ў кнізе на [GitHub](https://github.com/ukrmap/sinatra_api_examples).

## <a name="acknowledgments"></a>Падзякі

Я хачу падзякаваць менеджэраў і ўсіх інжынераў кампаніі [Facewatch](https://www.facewatch.co.uk/). Гэтая кніга існуе дзякуючы камандзе Facewatch і [Aejis](http://aejis.eu).