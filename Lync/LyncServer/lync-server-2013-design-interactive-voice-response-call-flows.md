---
title: Lync Server 2013： 設計互動式語音回應通話流程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Design interactive voice response call flows
ms:assetid: f3477f0a-3ad5-4b13-a73c-046aa451db19
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413020(v=OCS.15)
ms:contentKeyID: 48185826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78032a23fce6bb210ecec6eb828178aabddf9b52
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198136"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="design-interactive-voice-response-call-flows-in-lync-server-2013"></a>Lync Server 2013 中設計互動式語音回應通話流程

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-02-25_

您可以使用互動語音回應 (IVR) 以取得資訊從來電者與適當的佇列將來電導向。 問題和答案配對決定要使用哪一個佇列。 發話者的回應，根據來電者聽到的後續的問題，或路由傳送至適當的佇列。 時，IVR 問題和來電者的回應會提供給回應的代理程式人員接受來電提供給代理程式的重要資訊。

<div>

## <a name="overview-of-ivr-features"></a>IVR 功能概觀

回應群組應用程式提供語音辨識及文字轉換語音功能 26 語言。 您可以輸入使用文字轉語音] 或 wave (.wav) 或 Windows Media 音訊 (.wma) 檔案時，IVR 問題。 來電者可以使用語音或複頻式訊號 (DTMF) 回應回應。

互動工作流程最多支援兩層的問題，而每個問題最多會有四個可能的答案。 IVR 詢問來電者的問題，且來電者的回應，根據路由來電者傳送到佇列或詢問的第二個問題。 第二個問題最多也有四個可能的答案。 根據來電者對第二層問題的答案，可將來電者路由傳送到適當的佇列。

<div>


> [!NOTE]  
> 當您設計通話流程使用 Lync Server 管理命令介面時，您可以定義任何數字的層級的時，IVR 問題和答案的任何數字。 不過，針對來電者可用性，我們建議您使用不超過三個層級的問題，不超過五個解答。 此外，如果您在設計通話流程具有兩個以上的層級的四個以上解答的問題，您無法使用 Lync Server 2013 Control Panel 編輯通話流程。



</div>

時，IVR 問題和來電者的回應會提供給回應的代理程式接受來電者。

</div>

<div>

## <a name="working-with-speech-technologies"></a>使用語音技術

語音技術，例如語音辨識及文字轉語音]，可提升客戶體驗和更自然地且有效率地讓人員存取資訊。 不過，有時可能的發生其中指定的文字或使用者的語音回應無法識別正確的語音引擎。 例如，"\#」 符號由文字轉換語音引擎轉譯為 word 」 號碼。 」 這個問題，可以藉由下列減輕：

  - 語音引擎可讓來電者五個嘗試回答的問題。 如果來電者不正確地回答的問題 （亦即答案不是其中一個指定的回應） 或未提供所有，來電者取得解答若要回答這個問題的機會。 來電者有五個嘗試回答之前中斷的問題。 您可以設定每個來電者錯誤之後播放自訂的訊息 IVR。 問題重複每次。

  - 若要最小化環境雜訊解譯以回應語音引擎所可能使用較長的回應。 例如，回應應有多個音節，而且應該聲音明顯不同於其他每。

  - 如果您的問題有語音和 DTMF 回應，設定語音回應含有代表概念的文字，而不是 DTMF 回應。 例如，而不是使用 「 按下或說一個 」 使用 「 按 1 或說出帳單。 」

  - 在設計 ivr 時之後，呼叫工作流程、 聆聽提示、 回應給每個使用語音提示，並確認 IVR 聲音]，並如預期的行為。 然後，您可以修改過 ivr 後修正任何解譯問題。 遵循上述範例中，如果您需要參照到\#金鑰]，您可以修正您 IVR 提示字元中使用的索引鍵的名稱，而不是\#符號。 例如，「 按下以講話銷售，請按井字鍵。 」

</div>

<div>

## <a name="ivr-design-examples"></a>IVR 設計範例

下列各節包含不同 IVR 案例和問題和答案成對的範例。

<div>

## <a name="ivr-with-one-level-of-questions"></a>具有單層問題的 IVR

下列範例會顯示使用單層問題的 IVR。 它會使用語音辨識來偵測發話者的回應。

**Question:**「 謝謝您呼叫人力資源。 如果您想要轉接至薪資，說薪資。 否則請說出 HR。 」

  - **選取選項 1:** 來電者會路由傳送到薪資小組。

  - **選取選項 2:** 來電者會路由傳送到人力資源小組。

下圖顯示通話流程。

**單層互動通話流程**

![使用互動語音回應設計通話流程](images/Gg413020.4820a9f7-b5b0-4831-b972-baae0c015ec1(OCS.15).jpg "使用互動語音回應設計通話流程")

</div>

<div>

## <a name="ivr-with-two-levels-of-questions"></a>具有雙層問題的 IVR

下列範例會使用雙層問題的 IVR。 它可讓來電者使用語音或 DTMF 數字鍵台輸入來回應。

**Question:**「 謝謝您致電 IT Help Desk。 如果您有一個網路存取的問題，請按 1 或說出網路。 如果您有軟體發生問題，請按 2 或說出軟體。 如果您有硬體問題，請按 3 或說出硬體。 」

  - **選取選項 1:** 來電者會路由傳送到網路支援小組。

  - **選取選項 2:** 被詢問來電者後續問題：
    
    **Question:**「 若這是作業系統問題，請按 1 或說作業系統的系統。 如果這是內部應用程式有問題，請按 2 或說內部應用程式。 否則，請按 3 或說出其他。 」
    
      - **選取選項 1:** 來電者會路由傳送到作業系統支援小組。
    
      - **選取選項 2:** 來電者會路由傳送到內部應用程式支援小組。
    
      - **選取選項 3:** 來電者會路由傳送到軟體支援小組。

  - **選取選項 3:** 被詢問來電者後續問題：
    
    **Question:**「 若這是印表機問題按 1。 否則，請按 2。 」
    
      - **選取選項 1:** 來電者會路由傳送到印表機支援小組。
    
      - **選取選項 2:** 來電者會路由傳送到硬體支援小組。

下圖顯示通話流程。

**雙層互動通話流程**

![使用互動語音回應設計通話流程](images/Gg413020.a5b62083-312d-4419-898b-d1a225a5379f(OCS.15).jpg "使用互動語音回應設計通話流程")

</div>

</div>

<div>

## <a name="best-practices"></a>最佳做法

下列清單描述設計 ivr 時的一些最佳作法：

  - 可讓來電者快速進行工作。 避免提供太多資訊] 或 [在您 IVR 冗長的行銷郵件。

  - 如果您想要包含冗長的郵件，請考慮將它附加至第一個問題而不是歡迎訊息。 如果它屬於第一個問題回答問題，但他們無法略過的歡迎訊息，來電者可以略過郵件。

  - 說話發話者的語言。 避免 stilted 的語言。 自然地使用。

  - 寫入最快速且有效的提示。 移除不必要的任何選項。 結構資訊，讓來電者的預期回應是句子的結尾。 例如，「 轉接至業務小組，請按 1 」。

  - 使語音回應使用者易記。 例如，如果您指定 DTMF 和語音回應，使用類似下面的內容: 「 以轉接至業務小組，請按 1 或說出銷售 」。

  - 整個組織部署之前，請測試過 ivr 後的使用者群組。

</div>

</div>

<span> </span>

</div>

</div>

</div>

