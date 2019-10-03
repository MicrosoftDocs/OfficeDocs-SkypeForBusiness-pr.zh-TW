---
title: 設定雲端自動語音應答
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: waseemh
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 瞭解如何為 Microsoft 團隊設定及測試雲端自動語音應答。
ms.openlocfilehash: 0cac6b1bb7d19e91e4042bcb0673f6c677e77d2e
ms.sourcegitcommit: 2d31209aae9e0171693389db97b0b5c974864673
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2019
ms.locfileid: "37375706"
---
# <a name="set-up-a-cloud-auto-attendant"></a>設定雲端自動語音應答

自動語音應答讓撥入您組織的人員，並流覽功能表系統，以取得正確的部門、呼叫佇列、人員或接線員。 您可以使用 Microsoft 團隊系統管理中心，為您的組織建立自動語音應答。 若要建立新的自動語音應答，請移至左側導覽中的 [**語音**]，然後選取 [**自動助理** > **新增**]。

如果您想要深入瞭解自動語音應答，請參閱[什麼是雲端自動](/microsoftteams/what-are-phone-system-auto-attendants)語音應答？

> [!NOTE]
> 本文適用于 Microsoft 團隊和商務用 Skype Online。

## <a name="step-1--get-started"></a>步驟1：快速入門

- 必須有一個自動語音應答，才能擁有相關聯的資源帳戶。 如需資源帳戶及所有所需授權的詳細資料，請參閱[管理團隊中的資源帳戶](manage-resource-accounts.md)。

> [!TIP]
> 若要將來電重新導向給以**電話系統**授權為線上使用者的操作員或功能表選項，您必須啟用企業語音。 請參閱[指派商務用 Skype 授權](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses)或[指派 Microsoft 團隊授權](assign-teams-licenses.md)。 您也可以使用 Windows PowerShell。 例如，執行：`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

## <a name="step-2--create-a-new-auto-attendant"></a>步驟2：建立新的自動語音應答

> [!IMPORTANT]
> 每個自動語音應答都必須有一個相關聯的[資源帳戶](manage-resource-accounts.md)。 您必須先建立資源帳戶，然後才能將它與自動語音應答建立關聯。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft 團隊系統管理中心

在**Microsoft [團隊管理中心**] 中，按一下 [**語音** > **自動**語音應答]，然後按一下 [ **+ 新增**]：

#### <a name="general-info-page"></a>一般資訊頁面

![[我的自動助理] 頁面的螢幕擷取畫面](media/edacec94-9384-4a87-be0a-5c49a151287e.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

**名稱**輸入您自動語音應答的描述性顯示名稱。 名稱是必要的，而且最多可以包含64個字元，包括空格。 它會列在 [**自動**語音應答] 索引標籤的 [**名稱**] 欄中。

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

<a name="phonenumber"> </a>

**資源帳戶**按一下此按鈕以選取一或多個資源帳戶以連線到您的新自動語音應答。 必須有所有自動語音應答，才能擁有相關聯的資源帳戶。 資源帳戶可以有一個與該帳戶相關聯的電話號碼，但不需要電話號碼。 最上層的自動語音應答通常會有一個已指派電話號碼的資源帳戶，但嵌套的自動語音應答（用來做為第一級自動語音應答所連接的層級），可能不會有指派給其資源帳戶的電話號碼。

* * *

![在前一個螢幕擷取畫面](media/sfbcallout3.png)
 <a name="timezone"></a>中參照標注的數位3圖示

**時區**您必須為自動語音應答設定時區，但不需要對應給您組織的主要位址時區。 每個自動語音應答都可以有不同的時區，而且會根據您在此處選取的時區，設定自動語音應答的上班時間設定。

* * *

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

<a name="language"> </a>

**語言**從列出的任何可用語言中，選取您要用於自動語音應答的語言。 您在這裡設定的語言是自動語音助理用來與呼叫此自動語音應答的人員互動的語言，且所有系統提示都會以這種語言播放。

* * *

![在前一個螢幕擷取畫面中參照標注的數位5圖示](media/sfbcallout5.png)

<a name="operator"> </a>

**運算子**這是選擇性的，但您可以設定**運算子**選項，以允許呼叫者中斷功能表並向人員朗讀。

預設會將0按鍵指派給接線員。

如果您設定一個運算子，您也必須在 [商務用時**通話處理**] 頁面上的 [**編輯] 功能表選項**中，告訴誰呼叫有關該選項的人員。 如果您在自動語音應答上設定操作員，您必須在 [**呼叫者會聽到**] 方塊中輸入對應的提示文字，或變更您的音訊檔案，以包含此選項。 例如，"For 運算子，請按零。

您有幾種方式可以設定運算子：

- **貴公司中的人員**，在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。

     > [!Note]
     > **貴公司中的人員**可以是線上使用者，或使用商務用 Skype server 2015 或 Lync server 2013 主機內部部署的使用者。

- **語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。
- 您可以設定它，讓呼叫者傳送至語音信箱。 若要這樣做，請選取**貴公司中的人員**，並將此人的來電設定為直接轉接至語音信箱。

* * *

![在前一個螢幕擷取畫面中參照標注的數位6圖示](media/sfbcallout6.png)

**啟用語音輸入**如果選取此選項，就可以使用語音辨識。 通話中的人員可以使用[您所設定之語言](set-auto-attendant-languages-for-audio-conferencing-in-teams.md)的語音輸入。 如果您只想讓人員使用電話鍵台，您可以將語音辨識設定為 [關閉] 來停用。

* * *

當您完成選取專案時，請按 **[下一步]**。

#### <a name="business-hours-page"></a>[上班時間] 頁面

根據預設，上班時間會設定為 9:00 am 5:00 到星期五下午，星期一到星期五。 在上班時間之後，所有不包含在上班時間的時間都會被認為是在上班時間之後。 您可以按一下 [**選取 24/7** ]，以完成所有的上班時間。 除非您選取 [**選取 24/7** ] 選項，否則將會使用 [**下班後通話設定**] 頁面來設定自動語音應答在商務時間之後的通話處理規則。

![[上班時間] 頁面的螢幕擷取畫面](media/61769547-cdb4-45c0-af5a-3d6e0731fbc6.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

根據預設，上班時間設定為週一至週五，即 9:00 am-5:00 pm。 選取 [**清除所有時間**] 選項，以取消選取排程中的所有時間。 當您選取 [**重設為預設值**] 時，系統會將 [上班時間] 重設為 [週一至週五]，即 9:00 am-5:00

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

若要變更上班時間，請在 [行事曆] 中，醒目提示您要設定的上班時間。 行事曆可讓您以30分鐘的間隔來選取上班時間，您在此選取的上班時間是以您在 [**一般資訊**] 頁面上所設定的時區為基礎。 若要設定工間休息（例如午餐），請取消選取或拖曳以取消選取行事曆上的時間。 您可以在上班時間內設定多個工間休息。

* * *

當您完成選取專案時，請按 **[下一步]**。

#### <a name="business-hours-call-settings"></a>商務時間通話設定

> [!TIP]
> 如果您使用自訂的上班時間排程，您也必須在上班時間之後，使用 [**下班後通話處理**] 頁面來設定通話處理，這會提供與 [**商務時間通話] 設定**相同的選項。

您可以設定問候語、提示和功能表，讓使用者在營業期間聽到連結到貴組織的電話號碼。

![[上班時間通話處理] 頁面問候區段](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8.png)
![螢幕擷取畫面顯示 [上班時間通話處理] 頁面動作區段的螢幕擷取畫面](media/2a33b1f7-d362-47a7-bf32-ef702bc878e8b.png)

* * *

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

<a name="greetingsandrouting"> </a>

**問候語**商務時間問候語是選擇性的，而且可以設定為 [**無問候語**]。 在此情況下，來電程式在由您選取的其中一個動作處理之前，不會聽到訊息或問候。 您也可以上傳音訊檔案（.wav、mp3 或 .wma 格式），或使用文字轉換語音來建立自訂問候語。
- **上傳音訊**檔案如果您選擇此選項，請錄製問候語，然後上傳音訊檔案（以 .wav、mp3 或 .wma 格式）。
- **輸入問候訊息**如果您選擇此選項，請輸入您想要系統讀取的文字（最多1000個字元）。 例如，您可以輸入「歡迎使用 Contoso。 您的通話對我們很重要。」 在 [**呼叫者將會聽到**] 方塊中。

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

您可以選取在上班時間內到貨的通話情況。 您可以從下列動作中選擇：

<a name="redirectcalls"> </a>

- **中斷**連線如果您選取它，在聽到上班時間的問候之後，通話中的人員將會中斷連線。
- 重新**導向通話**這可以用來將來電自動傳送至：
  - **公司中的人員**，在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。 您可以將它設定為可將呼叫的人傳送給語音信箱。 若要這樣做，請選取 [**公司中的人員**]，並將 [此人] 設為 [將來電直接轉寄給語音信箱]

    > [!Note]
    > **公司中的人員**可以是線上使用者，或者是使用商務用 Skype server 2015 或 Lync server 2013 的使用者託管內部部署。

   - 其他**自動助理**

   您可以使用現有的自動助手來建立包含子功能表的第二層功能表選項。 這些稱為嵌套自動語音應答。 若要將呼叫傳送至嵌套的自動語音應答，請選取 [**公司] 中**的 [人員] 並指派已有關聯自動語音應答的人員，或在建立完此自動語音應答之後，就會與自動語音助理建立關聯的資源帳戶。

- 您也可以使用 [**播放] 功能表選項**，讓您設定您想要播放的提示。

* * *

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

**功能表提示**若要建立主功能表提示，您可以使用文字轉換語音或上傳音訊檔案（.wav、mp3 或 .wma）。 您可以在 [**設定您的呼叫者的功能表流覽**] 方塊中輸入提示，或錄製音訊檔案，例如：「銷售」，比如說或按下或說出1。 針對 [服務]，請按或說出 [2]。 如需客戶支援，請按或說出3。 針對運算子，請按或說出 [0]。 若要再次聆聽此功能表，請按星號鍵或說 [重複]。 **輸入問候訊息**如果您選擇這個選項，就應該輸入您想要系統讀取的文字（最多1000個字元）。 **上傳音訊**檔案如果您選擇此選項，您將需要錄製問候語，然後上傳音訊檔案（以 .wav、mp3 或 .wma 格式）。

* * *

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

**功能表選項設定**您可以新增或移除鍵盤上使用按鍵按鈕的功能表選項。 若要新增功能表選項，請按 **+ 指派撥號鍵**。 對應列的選項會顯示在下方。 若要刪除功能表選項，只需按一下 [小鍵盤] 控制項上對應鍵的左側，然後按一下上方的 [刪除] 圖示。 將會移除 [鍵對應] 列。

> [!TIP]
> 在新增至移除選項時，您必須更新功能表提示文字，或重新錄製音訊，因為現有的功能表提示不會自動完成。  
>
>任何順序都可以新增或移除任何功能表選項，而且鍵對應不一定是連續的。 例如，您可以建立一個含有鍵0、1和3的功能表，並對應至選項，而不使用鍵2。

> [!NOTE]
> 按鍵\* （重複）及\# （背面）是由系統所保留，而且無法重新指派。 如果已啟用語音辨識功能，按下 * 將與 "Repeat" 相對應，且 # 會與 "Back" 聲音命令相對應。

若要設定功能表選項，請在選取撥號鍵之後，您必須：

- 輸入選項的 [**語音] 命令**。 最多可包含64個字元，而且可以包含多個字，例如「客戶服務」或「作業與使用中」。 如果已啟用語音辨識功能，就會自動辨識名稱，而撥入的人員就可以按3，說出「三」，或者說「客戶服務」，選取對應至鍵3的選項。
- 如果按下對應的按鍵，或使用語音辨識來選取此選項，請選取要傳送通話的位置。 通話可以傳送至：

  - **運算子**如果已設定運算子，就會自動對應到 key 0，但是也可以將它刪除或重新指派給不同的金鑰。 如果運算子未設為任何鍵，語音命令 "Operator" 也將停用。
  - **貴公司中的人員**，在 Office 365 中已啟用企業語音或指派通話方案的**電話系統**授權。 您可以將它設定為可將呼叫的人傳送給語音信箱。 若要這樣做，請選取**貴公司中的人員**，並將其來電設定為直接轉接至語音信箱。

    > [!Note]
    > **貴公司中的人員**可以是線上使用者，或使用商務用 Skype Server 或 Lync server 2013 託管內部部署的使用者。

  - 其他**自動助理**

       您可以使用現有的自動助手來建立包含子功能表的第二層功能表選項。 這些稱為嵌套自動語音應答。 若要將呼叫傳送至嵌套的自動語音應答，請選取 [**公司] 中**的 [人員] 並指派已有關聯自動語音應答的人員，或在建立完此自動語音應答之後，就會與自動語音助理建立關聯的資源帳戶。

        > [!Note]
        > The **Business Hours** of nested (or second-level) auto attendants will also be used, including for the calls sent from other auto attendants that have been set up.

    - **語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。

* * *

![在前一個螢幕擷取畫面中參照標注的數位5圖示](media/sfbcallout5.png)

**依名稱撥號**如果您選擇這個選項，這會讓打電話給您的人員使用 [目錄搜尋] 搜尋貴組織中的人員。 您可以在 [**撥號作用**中] 頁面上設定這些選項，以選取哪些人員將被列為 [可用] 或 [無法供撥號使用]。 使用**電話系統**授權的任何線上使用者，或任何使用商務用 Skype Server 或 Lync server 2013 的使用者，都可以透過名稱來找到。

* * *

當您完成選取專案時，請按一下 **[下一步]**。

#### <a name="holiday-call-settings"></a>假日通話設定

<a name="holidaygreetings"> </a>

您最多可以將20個排定的假日新增至每個自動語音應答。

> [!TIP]
> 您可以在**組織內設定** > **假日**移至畫面來建立假日，或者您可以建立新的呼叫處理常式的一部分。

![[假日通話設定] 頁面的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

如果您已經建立其他自動語音應答，您可能會看到一個選項，您可以在此清單中使用或編輯您需要的專案。 如果不是，您將需要建立新的呼叫處理常式。

若要新增呼叫處理常式，請按一下 [ **+ 新呼叫處理常式**]。

* * *

![顯示新增呼叫處理常式的螢幕擷取畫面](media/50a5ce88-7f39-4210-808a-da7ced969854b.png)

![在前一個螢幕擷取畫面中參照標注的數位1圖示](media/sfbcallout1.png)

在新視窗中，在畫面頂端輸入新呼叫處理常式的名稱。

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

如果您的假日名稱已存在於 [**假日**] 下拉式清單中，您可以使用它。 如果您所需的假日名稱還不存在，請在下拉式清單中選取 [**建立新假日**]，然後在出現的新畫面中指定新假日的名稱和日期。 準備就緒時，按一下 [**儲存**]。

假日名稱最多可包含64個字元，且對於相同的自動語音應答必須是唯一的。 例如，在同一個自動語音應答中，您不能使用兩個名為 "感恩節" 的假日。

![在前一個螢幕擷取畫面中參照標注的數位3圖示](media/sfbcallout3.png)

**問候語**問候語是選擇性的，而且可以設定為 [**無問候語**]。 在這種情況下，在您選取的其中一個選項處理呼叫前，來電者將不會聽到任何訊息或問候語。 您也可以上傳音訊檔案（.wav、mp3 或 .wma 格式），或使用文字轉換語音來建立自訂問候語。

- **沒有問候語**在人員撥入自動語音應答電話號碼時，不會播放任何問候語。
- **上傳音訊**檔案如果您選擇此選項，請錄製假日問候語，然後上傳音訊檔案（以 .wav、mp3 或 .wma 格式）
- **輸入問候訊息**如果您選擇此選項，請輸入您想要系統讀取的文字（最多1000個字元）。 例如，您可以輸入「新年快樂！ 我們的辦公室目前已關閉。」 在 [**輸入問候訊息**] 方塊中。

![在前一個螢幕擷取畫面中參照標注的數位4圖示](media/sfbcallout4.png)

**動作**您可以選取在此假日期間到達的通話情況。 您可以從下列選項中選擇：

- **中斷**連線在聽到假日問候語之後撥入的人員將會中斷連線。
- 重新**導向通話**這可以用來將來電自動傳送至：
  - **貴公司中**擁有在 Office 365 中啟用企業語音或指派通話方案的**電話系統**授權的人員。 您可以將它設定為可將呼叫的人傳送給語音信箱。 若要這樣做，請選取**貴公司中的人員**，並將此人設定為讓其呼叫直接轉接至語音信箱。

    > [!Note]
    > **貴公司中的人員**可以是線上使用者，或使用商務用 Skype server 2015 或 Lync server 2013 主機內部部署的使用者。

   - **語音應用程式**選取與已建立之通話佇列或自動助理相關聯的資源帳戶名稱。

    > [!Note]
    > 根據預設，假期期間內的所有來電都會設定為在問候語（如果有的話）之後中斷連線，因此您必須指定重新導向（如果有其他行為的話）。

<a name="dialscope"></a>
#### <a name="select-dial-scope-page"></a>選取 [撥號作用域] 頁面

在此頁面上，您可以設定貴組織中的哪些使用者會列在您的目錄中，並可在撥入您組織的人員時，透過名稱撥號。

![顯示 [撥號作用中] 頁面的螢幕擷取畫面](media/1bcb185c-00db-43a7-b5c4-9b021c0627f7.png)

* * *

![數位1的圖示，參照前一個螢幕擷取畫面](media/sfbcallout1.png)中的標注使用 [**包括**] 選項，您有兩個選項：

- **所有的線上使用者**使用這個選項可讓您組織中的所有人員都包含在目錄搜尋中。 所有具備**電話系統**授權的線上使用者，以及使用商務用 Skype Server 或 Lync 2013 server （在 Office 365 中有通話方案）的使用者主機內部部署的使用者，都會列在其中。
- **自訂使用者群組**如果您使用這個選項，您可以搜尋已在您的組織中建立的 Office 365 群組、通訊群組清單或安全性群組，以及新增至此 Office 365 群組、通訊群組清單或安全性群組的人員，這些人必須**具備**使用商務用 Skype server 2015 或 Lync server 2013 的電話系統授權或主機內部部署。 您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。

* * *

![在前一個螢幕擷取畫面中參照標注的數位2的圖示](media/sfbcallout2.png)

使用 [**排除**] 選項，您有兩個選項：

- **None**使用這個選項，即表示不會從目錄搜尋中排除任何線上使用者。
- **自訂使用者群組**如果您使用這個選項，您可以搜尋已在貴組織中建立的 Office 365 群組、通訊群組清單或安全性群組，而且所有新增至此 Office 365 群組、通訊群組清單或安全性群組的人員將會從目錄搜尋中排除。 您可以新增多個 Office 365 群組、通訊群組清單和安全性群組。

> [!NOTE]
> 當有人透過語音辨識以名稱使用撥號時，最多可能需要36小時才能讓新的使用者將其名稱列在目錄中。

輸入所有必要的欄位並設定 [通話處理] 功能表和選項之後，請按一下 [**提交**]。

## <a name="editing-and-testing-auto-attendants"></a>編輯及測試自動語音應答

在您儲存了自動語音應答之後，它會列在 [**自動**語音應答] 頁面上。 這可讓您快速查看一些已設定的選項，包括姓名、電話號碼、語言和狀態。

如果您想要變更自動語音應答，請選取 [自動語音應答]，然後在 [動作] 窗格中按一下 [**編輯**]。

您也可以使用 [動作] 窗格中的 [**測試**] 按鈕，快速地將測試呼叫放到您的自動語音應答中。

## <a name="auto-attendant-cmdlets"></a>自動語音應答 Cmdlet

您也可以使用 Windows PowerShell 來建立及設定自動語音應答。 以下是您需要管理自動語音應答的 Cmdlet：

- [新-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)  
- [Set-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/set-csautoattendant?view=skype-ps)
- [CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/new-csautoattendant?view=skype-ps)
- [CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/get-csautoattendantholidays?view=skype-ps)
- [移除-CsAutoAttendant](https://docs.microsoft.com/powershell/module/skype/remove-csautoattendant?view=skype-ps)
- [新-CsAutoAttendantMenu](https://docs.microsoft.com/powershell/module/skype/new-csautoattendantmenu?view=skype-ps)
- [新-CsOnlineAudioFile](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineAudioFile?view=skype-ps)
- [新-CsAutoAttendantCallFlow](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallFlow?view=skype-ps)
- [Export-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/export-csorganizationalautoattendantholidays?view=skype-ps)
- [新-CsOnlineTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinetimerange?view=skype-ps)
- [新-CsOnlineDateTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csonlinedatetimerange?view=skype-ps)
- [新-CsOnlineSchedule](https://docs.microsoft.com/powershell/module/skype/New-CsOnlineSchedule?view=skype-ps)
- [CsAutoAttendantSupportedTimeZone](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedTimeZone?view=skype-ps)
- [新-CsAutoAttendantCallHandlingAssociation](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallHandlingAssociation?view=skype-ps)
- [CsAutoAttendantSupportedLanguage](https://docs.microsoft.com/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage?view=skype-ps)
- [匯入-CsAutoAttendantHolidays](https://docs.microsoft.com/powershell/module/skype/import-csautoattendantholidays?view=skype-ps)
- [新-CsAutoAttendantCallableEntity](https://docs.microsoft.com/powershell/module/skype/New-CsAutoAttendantCallableEntity?view=skype-ps)

### <a name="more-about-windows-powershell"></a>深入瞭解 Windows PowerShell

- Windows PowerShell 全部說明如何管理使用者，以及允許或不允許的使用者執行。 在 Windows PowerShell 中，您可以使用單一管理點管理 Office 365 和 Microsoft 團隊，當您有多個工作需要執行時，可簡化日常作業。 若要開始使用 Windows PowerShell，請參閱以下主題：

  - [Windows PowerShell 與 Lync Online 的簡介](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [為什麼需要使用 Office 365 PowerShell](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell 在速度、簡潔性和生產率上都有許多優點，只是使用 Microsoft 365 系統管理中心，例如當您在一次為多位使用者設定變更時。 請參閱下列主題，瞭解這些優點：

  - [使用 Office 365 PowerShell 管理 Office 365](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [使用 Windows PowerShell 管理商務用 Skype Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>相關主題

[以下是您在 Office 365 中使用電話系統所取得的結果](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[取得服務電話號碼](/microsoftteams/getting-service-phone-numbers)

[適用于音訊會議與通話方案的國家和地區可用性](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

[新-CsOrganizationalAutoAttendant](https://docs.microsoft.com/en-us/powershell/module/skype/new-csorganizationalautoattendant?view=skype-ps)  

[什麼是雲端自動語音應答？](what-are-phone-system-auto-attendants.md)

[小型企業範例-設定自動助手](/microsoftteams/tutorial-org-aa)  
