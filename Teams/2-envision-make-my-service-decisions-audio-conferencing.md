---
title: 建立語音會議服務決策-Microsoft 團隊
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 12/28/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 瞭解會議、授權及可用性、設定會議橋接器設定、取得或傳送電話號碼, 以及選擇租使用者撥號方案。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6f7c36904aadf19802511979fa5e069b3c91035e
ms.sourcegitcommit: 2f8b9c7c8d20f2605d09cae4bbaeb10667f2ddea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/21/2019
ms.locfileid: "36182739"
---
# <a name="make-my-service-decisions"></a>進行我的服務決策

若要規劃音訊會議的技術實現, 您必須提前進行一系列的服務決策, 以進一步準備貴組織來實施符合您所定義之業務需求的方案。

## <a name="audio-conferencing-in-teams"></a>團隊中的音訊會議

在 Microsoft 團隊中定義所需音訊會議功能的一部分, 第一個步驟就是評估最新的公開藍圖, 以判斷:

-   小組中要針對範圍中的使用者部署哪些音訊會議功能。

-   小組中的音訊會議預期使用者功能需求。

-   確認最新公開藍圖中所述之團隊的音訊會議功能可在您部署的時程表內滿足您的使用者、功能和範圍需求。

> [!NOTE]
> 您可以在<https://aka.ms/O365Roadmap>[部署] 中找到可識別團隊音訊會議功能的最新團隊藍圖。

## <a name="meetings-in-teams"></a>團隊中的會議

團隊可讓您的使用者使用 HD 影片、語音 IP (VoIP) 和 PSTN 電話撥入式會議選項, 來排程及加入線上會議。

會議可以安排為私人會議 (只有受邀的參與方可以加入) 或頻道會議 (針對有權存取頻道的所有使用者開啟), 而且您的使用者也可以在頻道內開始臨時會議。

> [!NOTE]
> 若要深入瞭解團隊中的會議功能, 請參閱[Microsoft 365 藍圖](https://aka.ms/O365Roadmap)。

如果您是透過市話或行動電話撥打電話給付費或免付費電話撥入式會議橋接電話號碼, 會議參與者就可以加入您的小組會議。 此外, 使用者也可以讓音訊會議服務啟動「撥號給我」功能, 讓他們可以使用 [聯絡人] 撥打電話 (適用于資料連線不可靠) 來參與會議, 或讓會議召集人邀請會議在參與者撥出電話的情況中進行。

> [!IMPORTANT]
> 小組中的音訊會議不支援協力廠商音訊會議提供者 (ACPs)。

<!--ENDOFSECTION-->

## <a name="availability-of-audio-conferencing"></a>音訊會議的可用性

在您規劃如何在團隊中實現音訊會議之前, 您必須先查看音訊會議服務的可用性, 以及[音訊會議與通話方案之國家和地區可用性](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)的詳細資訊。

> [!IMPORTANT]
> 根據法律限制, 對於要提供給跨國公司的音訊會議, Office 365 訂閱的合約必須源自可供商用的音訊會議服務所在的國家和地區。

確認貴組織有資格取得音訊會議服務之後, 請根據可用國家和地區的清單, 來編譯您要用來實施音訊會議服務的使用者位置或辦公室清單。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定哪些使用者位置或辦事處將會執行音訊會議服務。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>針對要啟用音訊會議服務的使用者位置或辦公室進行記錄。</li></ul>|

> [!TIP]
> 以下是音訊會議網站啟用清單範本的範例:
> 
> |辦事處   |位置 |PSTN 會議服務  |
> |---------|---------|---------|
> |單一 Epping 道路|澳大利亞|音訊會議|
> |100 Cyberport 公路|香港特別行政區|舊版 PSTN 會議|
> |一個 Marina Boulevard|新加坡|音訊會議|
> |32倫敦 Bridge 大街|英國|音訊會議|
> |39 quai du Président Roosevelt|法國|音訊會議|

<!--ENDOFSECTION-->

## <a name="licensing-for-audio-conferencing"></a>音訊會議的授權

[音訊會議授權](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)是提供給 Office 365 E5 訂閱者案的一部分, 或作為 Office 365 E1 或 Office 365 E3 訂閱者案的附加元件服務。

> [!NOTE]
> 團隊中的 PSTN 或電話撥入式會議不支援協力廠商音訊會議提供者 (ACPs)。
> <br>如果您目前已使用商務用 Skype Online PSTN 會議, 您可以立即在小組中利用音訊會議。

若要提供免付費的會議橋接器電話號碼, 並支援會議撥出到國際電話號碼, 您必須為貴組織設定[通訊點數](what-are-communications-credits.md)。

> [!IMPORTANT]
> 某些國家/地區僅由免付費的會議橋接器電話號碼提供服務。 若要支援這些國家/地區的撥入, 您必須使用通訊點數。

實施通訊點數時的第一個考慮是, 決定您想要購買的資金量。 如果您的組織選擇使用自動加值, 您必須決定觸發金額 (最小款項) 與自動加值金額。 您實際的使用方式會決定自動重新充電金額。 您應該監視您在一段時間內的通訊點數使用量, 並視需要調整充電金額。

您可以在[此](what-are-communications-credits.md)深入瞭解通訊點數。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>如果您的組織尚未購買所需的音訊會議授權, 請決定您是否要透過逐步執行現有的 Office 365 訂閱, 或購買音訊會議附加元件授權來取得音訊會議授權。</li><li>決定您的音訊會議實現是否需要通訊點數。 如果是, 請決定要購買的初始資金量。 在適當的地方, 決定觸發金額與自動重新充電金額。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄將指派音訊會議授權的使用者。</li><li>記錄通訊點數方案 (初始金額、觸發金額、自動重新充電金額)</li></ul>|

> [!TIP]
> 您可以使用下列範例, 將音訊會議使用者的授權指派清單記錄在檔中。
> 
> |使用者名  |辦事處  |Office 365 授權  |
> |---------|---------|---------|
> |Adele Vance|單一 Epping 道路|Office 365 E5|
> |立民 Wilber|單一 Epping 道路|Office 365 E3, 音訊會議附加元件|
> |Ben Walters|單一 Epping 道路|Office 365 E3, 音訊會議附加元件|
> |Christie Cline|一個 Marina Boulevard|Office 365 E3, 音訊會議附加元件|
> |Debra Berger|一個 Marina Boulevard|Office 365 E5|
> |先生|一個 Marina Boulevard|Office 365 E5|
> |Emily Braun|32倫敦 Bridge 大街|Office 365 E5|
> |Lidia Holloway|32倫敦 Bridge 大街|Office 365 E5|
> |港 Lahr|32倫敦 Bridge 大街|Office 365 E5|
> |Marcel Beauchamp|39 quai du Président Roosevelt|Office 365 E3, 音訊會議附加元件|
> |Rachelle Cormier|39 quai du Président Roosevelt|Office 365 E5|
> |Isabell Potvin|39 quai du Président Roosevelt|Office 365 E3, 音訊會議附加元件|

<br>

> [!TIP]
> 您的通訊點數規劃編號可以記錄如下:
>
> |         |         |
> |---------|---------|
> |初始金額|$1000|
> |觸發金額|$400|
> |自動重新充電金額|TBA|
> 
<!--ENDOFSECTION-->

## <a name="conference-bridge-phone-numbers"></a>[會議橋電話號碼]

Office 365 中的音訊會議服務包括:

-   多種類型的會議橋電話號碼 (免付費電話和免付費電話)

-   多個類別的會議橋接電話號碼 (專用和共用)

-   支援多種語言的會議橋接器 (主要和次要)

-   租使用者的預設電話號碼

> [!NOTE]
> 專用的會議橋接電話號碼會根據適用的授權數量, 計算出每個租使用者可以取得的電話號碼數限制。 免付費會議橋接器電話號碼需要通訊點數。

如果您必須將現有的會議橋接電話號碼轉接至音訊會議服務 (假設他們符合國家/地區特定的需求), 您可以將這些現有的會議橋接電話號碼轉接至 Microsoft。

> [!NOTE]
> 根據國家或地區、載波、涉及的電路數, 以及許多其他共同要素, 將電話號碼轉移至 Microsoft 的複雜度會大不相同。 使用您目前的提供者來調查可能會採取的時間, 以協助確保您的啟動程式足夠提前, 以符合您的時程表。

若要深入瞭解會議橋接器電話號碼, 請參閱下列文章:

-   [為 Microsoft 團隊設定音訊會議](set-up-audio-conferencing-in-teams.md)

-   [音訊會議的電話號碼](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/phone-numbers-for-audio-conferencing)

-   [取得服務電話號碼](getting-service-phone-numbers.md)

-   [將電話號碼傳送至 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您的組織是否需要專用的會議橋電話號碼。</li><li>決定如何取得適用于音訊會議的使用者位置或辦公室 (也就是從 Microsoft 取得或轉接現有的電話號碼) 的專用會議橋接電話號碼。</li><li>如果您選擇從 Microsoft 取得這些專案, 請決定要使用的方法 (表單提交或自動化) 來提供音訊會議的使用者位置或辦公室範圍。</li><li>決定要為每一個專用的會議橋接電話號碼設定的語言喜好設定。</li><li>決定租使用者預設的會議橋電話號碼。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄電話號碼取得的主計畫, 詳細說明在音訊會議實施範圍內, 每個使用者位置或 office 的電話號碼。</li><li>如果適用的話, 請完成新的電話號碼要求表單, 每個位置或辦公室一個表單。</li><li>記錄詳細的會議橋電話號碼設定 (共用及專用的會議橋電話號碼、每個專屬會議橋接電話號碼的語言喜好設定、租使用者預設的會議橋電話號碼)。</li></ul>|

以下是可用於捕獲會議橋接器詳細資料的範本範例。

> [!TIP]
> 以下是可捕獲會議橋接器詳細資料的範本範例:
> 
> |辦事處   |橋接號碼採集與橋輸入 |Bridge 編號  |Bridge 語言|
> |---------|---------|---------|---------|
> |單一 Epping 道路|取得新的專用|TBA|英文 (澳大利亞)|
> |一個 Marina Boulevard|取得新的共用|TBA|英文 (美國)、中文 (簡體、中國)|
> |32倫敦 Bridge 大街|埠現有、專用|+ 44 20 7946 0001|英文 (英國)|
> |39 quai du Président Roosevelt|取得新的專用|TBA|法文 (法國), 英文 (英國)|

<!--ENDOFSECTION-->

## <a name="conference-bridge-settings"></a>[會議橋] 設定

若要進一步調整使用者體驗, 您可以針對加入音訊會議會議 (會議進入與結束通知和本機號碼錄製)、會議召集人的 PIN 長度及電子郵件通知設定全組織的選項。

-   在錄製的名稱、電話號碼和色調等中, 都可以使用會議進入與結束通知。

-   PIN 長度可設定為4到12個數字, 並以5位數的 PIN 作為預設值。

-   預設會啟用 [音訊會議授權] 或任何其他系統管理員導向變更的已傳送通知電子郵件。 您可以停用這項功能, 並控制貴組織的使用者通訊。

針對獲指派音訊會議授權的使用者, 您可以將預設的免付費電話號碼 (顯示在音訊會議座標中) 設定為使用:

-   租使用者層級預設值。

-   自動指派的會議橋電話號碼。

-   針對每位使用者手動設定的會議橋電話號碼。

使用者專用的會議橋電話號碼通常適用于全球或全國組織, 使用者是在其中散佈, 而且必須在會議邀請中提供當地號碼做為預設的會議橋接電話號碼。

從不同的城市或海外加入的參與者可以查詢租使用者層級設定的其他號碼, 但這些號碼不會直接出現在會議邀請中。 會議邀請會提供一個連結, 讓參與者參與 [**小組會議撥入號碼**] 頁面, 讓他們查閱最接近其位置的會議橋接電話號碼。

您也可以設定每個個別會議召集人處理未獲驗證的呼叫者的方式, 無論是否要求會議召集人在未獲驗證的呼叫者獲准之前開始會議, 或允許未經驗證的呼叫者開始會議.

您也可以針對每個使用者套用其他設定, 以控制使用免付費會議橋接電話號碼和從會議撥出的電話號碼。

> [!NOTE]
> 這些與成本相關的控制項目前僅供預覽版客戶使用。 您可以在預覽計畫中註冊您的組織https://www.skypepreview.com。

您可以透過這些控制項, 決定會議召集人是否可以為組織的會議提供免付費會議電話號碼, 以及參與者是否可以從組織的會議撥出。 撥出控制等級的範圍是完全禁止撥出, 只允許撥出到國內號碼, 以便撥打國內和國際號碼。

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您的組織是否需要進入與結束通知, 以及 (如果有的話), 即要實施的通知類型 (聲調、電話號碼或錄製的名稱)。</li><li>決定符合您組織安全需求的音訊會議 PIN 長度。</li><li>決定您的組織是否想要控制與音訊會議服務相關的使用者通訊。</li><li>決定要指派給每個會議召集人的會議橋接電話號碼。</li><li>決定某些會議召集人是否需要使用免費的會議橋接電話號碼來進行會議。</li><li>決定某些會議召集人是否需要允許未經驗證的呼叫者開始會議。</li><li>決定某些會議召集人是否需要進行會議撥出, 以進行控制。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄詳細的會議橋接器設定 (進入和結束通知、PIN 長度、設定變更電子郵件通知)</li><li>檔要指派給每個會議召集人的會議橋接電話號碼, 以及用來控制未經驗證之呼叫者的原則以及免付費和撥出控制措施的相關設定。</li></ul>|

> [!TIP]
> 您可以在下列範例中記錄您的 [您的會議橋接] 設定。
> 
> |         |         |
> |---------|---------|
> |啟用會議進入和結束通知|後|
> |進入/結束宣告類型|聲調|
> |要求呼叫者在加入會議前記錄他們的名稱|禁止|
> |PIN 長度|500|
> |自動傳送電子郵件給使用者的撥入設定變更|禁止|

<br>

> [!TIP]
> 您可以使用下列範例, 為音訊會議使用者記錄「會議橋接」設定指派清單。
>
> |使用者名  |辦事處  |預設付費電話號碼  |預設免付費電話號碼  |允許免付費電話  |未驗證的呼叫者略過大廳  |會議撥出  |
> |---------|---------|---------|---------|---------|---------|---------|
> |Adele Vance|單一 Epping 道路|TBA|TBA|是的|後|國際及國內|
> |立民 Wilber|單一 Epping 道路|TBA|TBA|不|禁止|不允許|
> |Ben Walters|單一 Epping 道路|TBA|TBA|不|禁止|不允許|
> |Christie Cline|一個 Marina Boulevard|TBA|TBA|是的|禁止|家用|
> |Debra Berger|一個 Marina Boulevard|TBA|TBA|是的|後|家用|
> |先生|一個 Marina Boulevard|TBA|TBA|是的|後|家用|
> |Emily Braun|32倫敦 Bridge 大街|+ 44 20 7946 0001|TBA|是的|後|不允許|
> |Lidia Holloway|32倫敦 Bridge 大街|+ 44 20 7946 0001|TBA|是的|禁止|不允許|
> |港 Lahr|32倫敦 Bridge 大街|+ 44 20 7946 0001|TBA|是的|禁止|不允許|
> |Marcel Beauchamp|39 quai du Président Roosevelt|TBA|TBA|不|禁止|家用|
> |Rachelle Cormier|39 quai du Président Roosevelt|TBA|TBA|是的|後|國際及國內|
> |Isabell Potvin|39 quai du Président Roosevelt|TBA|TBA|不|禁止|家用|

<!--ENDOFSECTION-->

## <a name="manage-cloud-voice-telephone-numbers"></a>管理雲端語音電話號碼

針對音訊會議的實現, 您可以選擇取得新的電話號碼或轉移/埠現有的電話號碼。

若要讓使用者以您習慣的方式撥打電話號碼 (例如忽略當地電話的區功能變數代碼、忽略國內通話的國家/地區碼), 或是在執行會議撥出時使用短數位撥號, 您可以設定自訂的撥號方案然後將它指派給使用者。

## <a name="acquire-new-telephone-numbers"></a>取得新的電話號碼

Microsoft 雲端語音解決方案中的兩種電話號碼類型如下:

-   訂閱者 (使用者) 編號, 可指派給您組織中的使用者。

-   服務號碼, 提供付費和免付費服務號碼 (其併發通話容量高於訂閱者號碼), 而且可以指派給諸如音訊會議、自動語音應答或通話佇列等服務。

如需這些電話號碼類型的詳細資訊, 請參閱[通話方案所用的不同類型的電話號碼](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/different-kinds-of-phone-numbers-used-for-calling-plans)。

您可以取得的電話號碼總數, 取決於電話號碼類型, 以及您已購買並指派給使用者的授權數量。

在服務號碼方面, 您必須仔細規劃音訊會議的部署。 評估您的企業是否需要專用的會議橋電話號碼;如果不是, 您的組織可以選擇使用共用的會議橋電話號碼。

如需您可以取得的電話號碼總計數的詳細資訊, 請參閱[您可以取得多少電話號碼？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/how-many-phone-numbers-can-you-get)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定將從 Microsoft 取得新電話號碼的使用者位置或辦公室。</li><li>決定要從 Microsoft 取得的電話號碼類型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將從 Microsoft 取得新電話號碼的使用者位置或辦公室記錄在檔中。</li><li>檔要從 Microsoft 取得的電話號碼類型。</li></ul>|

## <a name="transfer-existing-telephone-numbers"></a>轉移現有的電話號碼

如果您的組織想要將現有的電話號碼轉移 (或埠) 至 Microsoft, 您可以透過將埠訂單要求提交給 Microsoft 來執行此動作。

您可以一次轉移所有現有的電話號碼 (完整埠), 並在部分市場中, 您可以轉移現有電話號碼的子集 (部分埠)。 部分埠在您只想要將電話撥入式會議橋接器移至音訊會議服務的情況下, 可能會很有用。

單一端口順序只能將電話號碼轉移到單一電話號碼類型。 如果您需要將部分電話號碼作為訂閱者號碼或作為服務號碼的傳輸, 我們建議您先完成轉移至 Microsoft, 然後在數位位於 Microsoft 控制權中時立即執行轉換。

或者, 如果支援部分埠, 您可以一次提交多個埠要求 (一個埠要求)。 不過, 這個替代方法會將您的合約延長到您現有的電訊服務提供者。

電話號碼移植是一個複雜的主題, 需要進行完整的規劃、協調及充分管理您的專案關係人預期。 若要深入瞭解, 請參閱下列文章:

-   [將電話號碼傳送到 Office 365](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transfer-phone-numbers-to-office-365)

-   [傳送電話號碼常見問題](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/transferring-phone-numbers-common-questions)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定現有電話號碼會傳送至 Microsoft 的使用者位置或辦公室。</li><li>決定要傳送給 Microsoft 的電話號碼類型。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>將現有電話號碼傳送至 Microsoft 的使用者位置或辦公室記錄在檔中。</li><li>檔要傳送給 Microsoft 的電話號碼類型。</li></ul>|

<!--ENDOFSECTION-->

## <a name="dial-plans"></a>撥號方案

Office 365 的 [電話系統] 功能中的撥號方案是一組正常化規則, 可將撥打的電話號碼轉換成替代格式 (通常是164個格式), 用於呼叫授權及呼叫路由。 音訊會議服務會利用電話系統所用的相同功能, 在會議撥出案例中轉譯撥打的電話號碼 (例如, 透過 PSTN 邀請參與者並撥回 [呼叫我] 功能)。

在 Office 365 的 [電話系統] 功能中, 有兩種類型的撥號方案:

-   [**服務撥號方案]:** 這是根據使用者的 Office 365 使用位置所套用的預設撥號計畫, 且無法加以修改。

-   **租使用者撥號方案:** 這是租使用者中可自訂的撥號方案, 會進一步分為兩種類型:

    -   **租使用者-全域撥號方案:** 套用至租使用者中所有使用者的撥號計畫。

    -   **租使用者撥號方案:** 僅適用于特定使用者的撥號方案。

指派給使用者的有效撥號方案是服務撥號方案 (根據使用者的 Office 365 使用位置) 與租使用者撥號方案 (可以是租使用者的全域撥號方案或租使用者撥號方案) 的組合。

![表格顯示三種服務與租使用者撥號方案組合。](media/audio_conferencing_image8.png "表格顯示三種服務與租使用者撥號方案組合。")

> [!Important]
> 每個租使用者撥號方案中最多可以有25個正常化規則;因此, 請務必避免複製已提供給服務撥號方案中的正常化規則。

若要深入瞭解撥號方案, 請參閱[什麼是撥號方案？](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)

<br>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" />|決策點|<ul><li>決定您的組織是否需要自訂的撥號方案 (業務需求、採納需求等)。</li><li>如果適用, 請決定租使用者撥號方案 (租使用者或租使用者) 的範圍, 以支援自訂撥號方案的需求。</li><li>如果適用, 請決定您要建立的租使用者撥號方案, 以支援雲端語音實現的範圍內的使用者位置或分支機搆。</li><li>如果適用, 決定要為每位使用者指派自訂撥號方案和租使用者撥號計畫。</li></ul>|
|<img src="media/audio_conferencing_image9.png" />|後續步驟|<ul><li>記錄自訂的撥號方案, 以及相關聯的正常化規則, 以設定為雲端語音實現的一部分。</li><li>記錄指派自訂撥號方案的使用者, 以及要指派給每個使用者的租使用者撥號計畫。</li></ul>|

> [!TIP]
> 如果適用于您的專案, 您可以使用下列範本來記錄租使用者撥號方案設定。
> 
> |租使用者撥號方案名稱<br>_說明_  |正常化規則名稱<br>_說明_  |模式<br>翻譯<br>IsInternalExtension  |
> |---------|---------|---------|
> |**AU-NSW-NorthRyde-OER**<br>_一 Epping 公路 Ryde, NSW, AU 撥號方案_|**AU-NSW-NorthRyde-OER-內部**<br>_一個 Epping 公路 office、北 Ryde、NSW、澳大利亞的內部號碼 (x7000-x7999)_|^ (7 \ d{3}) $<br>+ 6125550 $ 1<br>滿足|
> ||**AU-NSW-本機**<br>_NSW、澳大利亞的當地數位正常化_|^ ([2-9] \d{7}) $<br>+ 612 $ 1<br>虛假|
> ||**AU-TollFree**<br>_澳大利亞免付費電話號碼標準化_|^ (1 [38] \d{4,8}) \d * $<br>+ 61 $ 1<br>虛假|
> ||**AU-服務**<br>_澳大利亞服務號碼標準化_|^ (000\|1 [0125] \d{1,8}) $<br>$1<br>虛假|
> |**SG-新加坡-OMB**<br>_OMB 新加坡, SG 撥號方案_|**SG-OMB-內部**<br>_OMB office、新加坡的內部號碼 (x8000-"x8999")_|^ (8 \ d{3}) $<br>+ 656888 $ 1<br>滿足|
> ||**SG-TollFree**<br>_適用于新加坡的免費電話號碼標準化_|^ (1？ 800 \ d{7}) \d * $<br>+ 65 $ 1<br>虛假|
> ||**SG 服務**<br>_適用于新加坡的服務號碼標準化_|^ (1 \ d{3,4}\|9 d{2}) $<br>$1<br>虛假|
> |**FR-巴黎-Issy-39qdPR**<br>_39 quai du Président Roosevelt Issy-果-Moulineaux, 法國撥號方案_|**FR-39qdPR-內部**<br>_在 39 quai du Président Roosevelt office、Issy-果-Moulineaux、法國的內部號碼 (x7000-"x7999")_|^ (7 \ d{3}) $<br>+ 3319999 $ 1<br>滿足|
> ||**FR-TollFree**<br>_法國免付費電話號碼標準化_|^ 0？(80 \ d{7}) \d * $<br>+ 33 $ 1<br>虛假|
> ||**FR-服務**<br>_法國的服務編號正常化_|^ (1 \ d{1,2}\|11 [68] \d{3}\|10 \ d{2}\|3 \ d{3}) $<br>$1<br>虛假|

<br>

> [!TIP]
> 您可以利用下面的範例範本來記錄撥號計畫作業, 以支援您的專案:
>
> |使用者名  |辦事處  |撥號方案類型  |撥號方案名稱  |
> |---------|---------|---------|---------|
> |Adele Vance|單一 Epping 道路|租使用者撥號方案|AU-NSW-NorthRyde-OER|
> |立民 Wilber|單一 Epping 道路|租使用者撥號方案|AU-NSW-NorthRyde-OER|
> |Ben Walters|單一 Epping 道路|租使用者撥號方案|AU-NSW-NorthRyde-OER|
> |Christie Cline|一個 Marina Boulevard|租使用者撥號方案|SG-新加坡-OMB|
> |Debra Berger|一個 Marina Boulevard|租使用者撥號方案|SG-新加坡-OMB|
> |先生|一個 Marina Boulevard|租使用者撥號方案|SG-新加坡-OMB|
> |Emily Braun|32倫敦 Bridge 大街|[服務撥號方案]|N/A|
> |Lidia Holloway|32倫敦 Bridge 大街|[服務撥號方案]|N/A|
> |港 Lahr|32倫敦 Bridge 大街|[服務撥號方案]|N/A|
> |Marcel Beauchamp|39 quai du Président Roosevelt|租使用者撥號方案|FR-巴黎-Issy-30qdPR|
> |Rachelle Cormier|39 quai du Président Roosevelt|租使用者撥號方案|FR-巴黎-Issy-30qdPR|
> |Isabell Potvin|39 quai du Président Roosevelt|租使用者撥號方案|FR-巴黎-Issy-30qdPR|

<!--ENDOFSECTION-->

## <a name="document-service-decisions"></a>檔服務決策 

使用本文前幾節中的資訊來記錄您的服務決策。 一般來說, 本檔將包含下列主要章節:

-   音訊會議服務網站啟用清單

-   音訊會議會議召集人的授權指派清單

-   通訊點數規劃編號

-   [會議橋] 詳細資料

-   [會議橋] 設定

-   [會議橋] 設定指派

-   電話號碼購買方案

-   租使用者撥號方案

-   撥號方案指派

<!--ENDOFSECTION-->