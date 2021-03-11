---
title: 什麼是移轉訂單？
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: 概觀瞭解什麼是移轉訂單，以及如何將電話號碼從服務提供者移轉至 Teams。
ms.openlocfilehash: d7ca4769dcd1f320a7d0b8a8ed18fdba5b06abbd
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615049"
---
# <a name="whats-a-port-order"></a>什麼是移轉訂單？

如果您目前擁有電話服務提供者或電信業者，而且已經有使用者或服務的電話號碼，您必須建立「移轉訂單」，才能將這些電話號碼移轉至 Microsoft Teams。 當號碼經過埠時，您可以將這些電話號碼指派給使用者和服務，例如音訊會議 (會議橋接器) 、自動語音機和通話佇列。
  
將電話號碼埠到 Teams 之後，Microsoft 會變成您的服務提供者，您可以中斷服務與舊的服務提供者或電信公司之間的連接。

請詳閱本文中的資訊，以熟悉號碼埠。 之後，您應該可以建立移轉訂單並移轉電話號碼。 請參閱 [將電話號碼轉接到 Teams](transfer-phone-numbers-to-teams.md) 以逐步指示。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些國家/地區支援號碼埠？

您可以在所有支援的國家/地區移轉或移轉電話號碼，但您提交移轉訂單要求方式取決於電話號碼的發自國家/地區或區域。 有關支援號碼埠的國家和地區清單，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  

目前 [，Microsoft](transfer-phone-numbers-to-teams.md) Teams 系統管理中心的埠精靈支援取得英國、美國和加拿大的電話號碼。 若要取得其他國家/地區的電話號碼，您可以手動 [提交埠訂單](manually-submit-port-order.md)。
  
## <a name="what-numbers-can-be-transferred"></a>哪些號碼可以移轉？

 **您可以移轉**
  
一般而言，您可以移轉來自支援提供者的任何電話號碼，包括：
  
- 市話電話號碼。

- 行動裝置電話號碼，例如用於手機和平板電腦的電話號碼。

    > [!NOTE]
    > 移轉行動電話號碼僅適用于美國和波多黎各。
  
- 付費電話號碼。

- 免付費電話號碼。

    > [!NOTE]
    > 通用國際免費電話號碼 (UIFN) 無法傳輸給我們。 
  
- 服務電話號碼，例如會議橋接器、自動電話機等使用的號碼。

- 傳真呼叫號碼，但無法用來傳真。 他們必須被指派給使用者。

- 來自電話提供者的 VoIP 電話號碼，例如 Vonage 或 RingCentral。

- 商務用 Skype 混合式電話號碼。 如果您想要移轉這些號碼，請以電子郵件傳送給我們 <ptn@microsoft.com> 。

  **無法傳輸：**
  
    > [!NOTE]
    > 目前，您無法移轉任何不支援之國家/地區的電話號碼，包括 VoIP 電話提供者的電話號碼。 有關支援的國家/地區清單，請參閱音訊會議與通話方案的國家[/](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)地區可用性
  
- 用於資料連線的電話號碼，例如用於資料線路或寬頻網際網路連接。

- 傳真專用的電話號碼。

    如果您現有的專用電話號碼正用於傳真，您可以將這些號碼移轉至 Teams，但傳真服務無法如預期繼續工作。  Teams 客戶無法使用傳真服務，即使您擁有電話系統、國內通話方案或國際通話方案授權。

    如果您將電話號碼埠至 Teams，您可以將這個電話號碼指派給貴組織的使用者，而不是使用它來傳真。

    > [!NOTE]
    > 目前英國不支援傳輸英國的非地區號碼，包括區碼 0843、0844、0845、0870、0871、0872 的共用成本號碼。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些資訊？

您必須擁有目前電信公司的所有帳戶資訊。 在埠訂單中輸入的資訊大多位於您目前服務提供者的最新帳單或發票上。 您也需要知道帳戶名稱是誰，以及要端口的號碼。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什麼是完整埠和部分埠移轉？

當您將電話號碼移轉至 Teams 時，您可以選擇轉接所有號碼或部分號碼。
  
- **完整埠** 此時，您將所有號碼從目前的服務提供者移轉至 Teams。 當系統詢問要移轉的電話號碼時，您必須包含帳單電話號碼 ( BTN) 以及您帳戶上所有其他的電話號碼。

    例如，假設您的 BTN 是  *+1 425-555-1234，*  而您想要將 25 個電話號碼全部 (*+1 425-555-1235 到 1259*) 。 當您按照下列指示移轉號碼時，請輸入 **：+14255551234 - +14255551259。**

- **部分埠** 此時，您只會將部分電話號碼從目前的服務提供者移轉到 Teams。 當您想要將部分電話號碼系結至相同的 BTN 時 *，*** 不得包含 ** BTN 以及您帳戶上所有其他的電話號碼。

    例如，假設您的 BTN  *是 +1 425-555-1234，*  而您想要只埠 25 個電話號碼中的 5 個 (*+1 425-555-1235 到 1259*) 。 當您按照下列指示移轉號碼時，請輸入 **：+1 425 555 1235 - +1 425 555 1239。**
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我可以一次提交所有號碼的單一號碼埠要求嗎？
<a name="bkmk_type_1"> </a>

每個電信公司需要一個唯一的要求，以及要端口的號碼類型。
  
例如，您需要針對下列每種號碼類型提交唯一號碼埠要求：
  
- 當地付費電話號碼，也稱為訂閱者號碼或地理位置號碼

- 具有區碼的免付費電話號碼，例如：800、844、855、866、877 和 888

- 行動電話號碼

- 可在 Microsoft 365 或 Office 365 中用於音訊會議的服務號碼。

以下提供如何針對每種號碼類型提交號碼埠要求之詳細資訊：
  
- **不同電信** 公司提供的電話號碼需要每個電信公司提供的唯一號碼埠要求。

- 包含區碼的免付費號碼，例如：800、844、855、866、877 和 888，無法包含在號碼埠要求中，其他號碼類型。 若要端口這些免付費號碼，您必須手動 [提交埠訂單](manually-submit-port-order.md)。 您無法將這些數位在 Microsoft Teams 系統管理中心進行埠。 詳細資訊請參閱管理 [您組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    請針對國家/ (LOA) 以及要端口的電話號碼類型，使用正確的授權信。 您可以[在這裡下載所需的 LOA。](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

- **行動電話號碼** 需要 PIN 碼才能授權傳輸。 因此，他們需要個別的號碼埠要求。

- **服務編號** 的埠要求必須自行提交。 無法以其他類型的數位提交。

## <a name="how-long-does-it-take-to-port-numbers"></a>埠號碼需要多久時間？
<a name="bkmk_type_1"> </a>

完成埠訂單要求後，需要 7 到 14 天的時間處理。 不過，視您的服務提供者而異，最多可能需要 30 天。 電話號碼經過埠之後，您就會收到我們的電子郵件，讓您知道您好。
  
若要檢查您的埠訂單狀態，請在 Microsoft Teams 系統管理中心的左側流覽中，前往 **語音**  >  **電話號碼**，然後按一下 [訂單 **記錄**。 每個埠訂單狀態會列在狀態 **欄中** 。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>使用者能否 (訂閱) 電話號碼轉換成服務號碼？
<a name="bkmk_type_1"> </a>

可以。 您只需要提交服務要求，其中包含貴組織的租使用者 GUID 和您想要轉換的電話號碼。 若要這麼做，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>我可以將號碼從 Teams 埠到不同的電話服務提供者或電信公司嗎？

若要將號碼從 Teams 埠到不同的電信公司，您必須向新的電信公司提交要求。 您也需要在 Microsoft Teams 系統管理中心設定埠 PIN。

若要定義您的埠 PIN，請在 Microsoft Teams 系統管理中心的左側流覽中，前往頁面右上角的語音電話號碼，選取管理埠  >  **** **PIN，** 然後輸入 10 位數 PIN。

當您的新電信公司向我們提出埠要求時，我們會要求他們提供您定義的 PIN。

## <a name="common-mistakes-to-watch-out-for"></a>要留意的常見錯誤
<a name="bkmk_type_1"> </a>

數位埠很容易進行。 不過，如果電話服務提供者發生問題、訂單不完整且資訊遺失，或是有錯字，您的訂單可能會亂七八糟。
  
以下是客戶在埠號碼時最常看到的錯誤。 將電話儲存給客戶支援，然後仔細檢查這些錯誤。
  
- 請確定您提供的帳戶資訊與電信電信公司記錄的完全一樣。 資訊不一致是錯誤和延遲您埠訂單最常見的原因。 確認下列為 True：

  - 經授權變更帳戶的名稱或人員是正確的。

  - 位址正確。

  - 帳戶號碼正確無誤。

  - BTN 是正確的。

- 請確定這些電話號碼上未啟用進位的通話控制功能，例如通話搜尋、特殊鈴聲。

- 請確定您尚未下任何新服務訂單，或中斷與目前服務提供者的連線。

- 請確定所有號碼都來自同一個電信公司與同一個帳戶。

- 請確定您的服務為使用中。 凍結帳戶可防止帳戶上的電信者變更。 獲授權變更帳戶的人員必須提交訂單給目前的電信公司，才能移除凍結。 視電信公司不同，此程式可能需要一到三周的時間。

## <a name="related-topics"></a>相關主題

- [您的移轉訂單狀態為何？](port-order-status.md)
- [用於通話方案的電話號碼類型](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
