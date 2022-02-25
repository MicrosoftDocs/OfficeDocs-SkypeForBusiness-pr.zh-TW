---
title: 什麼是移轉訂單？
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.voice.phonenumbers.porting.overview
- Calling Plans
description: 概觀什麼是移轉訂單，以及如何將服務提供者的電話號碼移轉Teams。
ms.openlocfilehash: bb9ebd91b1f5a08fb07eff0f469be4496714ecfc
ms.sourcegitcommit: 766199440a152d97c95c2c45b7c4654815e64d9a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/25/2022
ms.locfileid: "62963414"
---
# <a name="whats-a-port-order"></a>什麼是移轉訂單？

如果您目前擁有電話服務提供者或電信業者，而且已經有使用者或服務的電話號碼，您必須建立「移轉訂單」，才能將這些電話號碼Microsoft Teams。 當號碼經過移植時，您可以將這些電話號碼指派給使用者和服務，例如會議橋接器 (、自動語音) 和通話佇列的音訊會議服務。
  
將電話號碼移植到 Teams之後，Microsoft 會成為您的服務提供者，您可以中斷與舊服務提供者或電信公司的服務。

請閱閱本文中的資訊，以熟悉數位埠。 之後，您應該準備好建立移轉訂單並傳輸電話號碼。 請參閱[將電話號碼轉接Teams](transfer-phone-numbers-to-teams.md)，以逐步指示。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些國家/地區支援號碼移植？

您可以在所有支援的國家/地區移轉或移轉電話號碼，但您提交移轉訂單要求的順序取決於電話號碼來自的國家/地區。 有關支援號碼移植的國家和地區清單，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  

目前，[系統管理中心中的](transfer-phone-numbers-to-teams.md)Microsoft Teams精靈支援取得英國、美國和加拿大的電話號碼。 若要取得其他國家/地區的電話號碼，您可以 [手動提交埠訂單](manually-submit-port-order.md)。
  
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
    > 通用國際免費電話號碼 (UIFN) 無法移轉至我們。 
  
- 服務電話號碼，例如用於會議橋接器、自動電話機等的電話號碼。

- 傳真呼叫號碼，但無法用於傳真。 他們必須指派給使用者。

- 來自電話提供者的 VoIP 電話號碼，例如 Vonage 或 RingCentral。

- 商務用 Skype混合式電話號碼。 如果您想要移轉這些數位，請傳送電子郵件給我們。 <ptn@microsoft.com>

**您無法傳輸：**
  
> [!NOTE]
> 目前，您無法移轉任何不受支援國家/地區的電話號碼，包括 VoIP 電話提供者的電話號碼。 有關支援的國家/地區清單，請參閱音訊會議與通話方案的國家/ [地區可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 電話用於資料連線的數位，例如DSL 線路或寬頻網際網路連接。

- 電話傳真專用號碼。

    如果您有用於傳真的現有專用電話號碼，您可以將這些數位移轉至Teams但傳真服務無法如預期繼續工作。 即使您擁有傳真服務、國內Teams方案或國際通話方案電話系統傳真服務也一樣。

    如果您將電話號碼Teams，您可以將這個電話號碼指派給貴組織的使用者，而不是使用它進行傳真。

> [!NOTE]
> 目前在英國，我們目前不支援傳輸英國非地理號碼，包括區碼 0843、0844、0845、0870、0871、0872 的共用成本號碼。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些資訊？

您必須擁有目前電信公司的所有帳戶資訊。 您于埠訂單中輸入的資訊，大多可于您目前服務提供者的最新帳單或發票上找到。 您也需要知道帳戶上的名稱，以及要端口的號碼。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什麼是完整埠和部分埠傳輸？

當您將電話號碼移轉至Teams，您可以選擇轉接所有號碼或部分號碼。
  
- **完整埠** 這是當您將目前服務提供者的所有號碼移轉至Teams。 當系統要求您轉接電話號碼時，您必須包含帳單電話號碼 (BTN) 以及您帳戶上所有其他電話號碼。

    例如，假設您的 BTN 是  *+1 425-555-1234*  ，而您想要將 25 個電話號碼 (*+1 425-555-1235 到 1259*) 。 當您按照下列指示傳送號碼時，請輸入： **+14255551234 - +14255551259**。

- **部分埠** 此時，您只會將部分電話號碼從目前的服務提供者轉接至Teams。 當您想要將部分電話號碼與同一個 BTN 系結在一起時， *您 ** 不得* 包含 ** BTN 以及您帳戶上所有其他電話號碼。

    例如，假設您的 BTN 是  *+1 425-555-1234*  ，而您只想將 25 個電話號碼中的 5 個 (*+1 425-555-1235 到 1259*) 。 當您按照下列指示傳送號碼時，請輸入： **+1 425 555 1235 - +1 425 555 1239**。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我可以一次提交所有號碼的單一號碼移植要求嗎？
<a name="bkmk_type_1"> </a>

每個電信公司需要一個唯一的要求，以及要移植的號碼類型。
  
例如，您需要針對下列每種數位類型提交唯一的數位移植要求：
  
- 當地付費號碼，也稱為訂閱者號碼或地理號碼

- 不含區碼的免付費號碼，例如：800、844、855、866、877 和 888

- 行動電話號碼

- 可在會議或會議中使用的服務號碼Microsoft 365 Office 365。

以下是如何針對每種數位類型提交號碼移植要求之詳細資訊：
  
- **電話不同** 電信公司所提供的號碼，需要針對每個電信公司所提供的號碼提出唯一的移植要求。

- **不含區** 碼的免付費號碼，例如：800、844、855、866、877 和 888，無法包含在號碼移植要求中，並包含其他類型的號碼。 若要端口這些免付費號碼，您必須 [手動提交埠訂單](manually-submit-port-order.md)。 您無法將這些數位Microsoft Teams系統管理中心。 詳細資訊，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    請針對國家/地區使用正確的授權 (LOA) ，以及您想要端口的電話號碼類型。 您可以 [在這裡下載所需的 LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- **行動電話號碼** 需要 PIN 碼才能授權傳輸。 因此，他們需要個別的號碼埠要求。

- **服務號碼** 的埠要求必須自行提交。 無法與其他數位類型一起提交。

## <a name="how-long-does-it-take-to-port-numbers"></a>埠號碼需要多久時間？
<a name="bkmk_type_1"> </a>

完成埠訂單要求之後，處理需要 7-14 天。 不過，視您的服務提供者而異，最多可能需要 30 天。 電話號碼經過移植之後，您就會收到我們的電子郵件，讓您知道您很好。
  
若要檢查您的埠訂單狀態，請在系統管理中心的左側導Microsoft Teams，前往 **[語音**  >  電話號碼，然後按一下 **[** 訂單 **歷程記錄**。 每個埠訂單狀態會列在狀態 **欄中** 。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>使用者或 () 電話號碼可以轉換成服務號碼嗎？
<a name="bkmk_type_1"> </a>

是的，他們可以。 您只需要提交服務要求，其中包含貴組織的租使用者 GUID 和您想要轉換的電話號碼。 若要這麼做，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>我可以將號碼從手機Teams到不同的電話服務提供者或電信公司嗎？

若要將號碼從Teams到不同的電信公司，您必須向新的電信公司提交要求。 您也需要在系統管理中心設定Microsoft Teams PIN。

若要定義您的埠 PIN，請在 Microsoft Teams 系統管理中心的左側流覽中，前往頁面右上角的語音  >  **電話** 號碼，選取管理埠 **PIN**，然後輸入 10 位數 PIN。

當您的新電信公司向我們提出移植要求時，我們會要求他們提供您定義的 PIN。

如果您需要進一步設定 PIN，請聯絡 [電話號碼服務小組](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>要留意的常見錯誤
<a name="bkmk_type_1"> </a>

數位埠很容易進行。 不過，如果電話服務提供者發生問題、訂單不完整且遺失資訊，或是有錯字，您的訂單可能會亂七八糟。
  
以下是客戶在埠號碼時最常犯的錯誤。 請給自己儲存電話給客戶支援，然後仔細檢查這些錯誤。
  
- 請確定您提供的帳戶資訊與手機電信公司的記錄完全一樣。 資訊不一致是錯誤及延遲埠訂單最常見的原因。 確認下列專案為 True：

  - 有權變更帳戶的名稱或人員正確無誤。

  - 位址正確。

  - 帳戶號碼正確。

  - BTN 是正確的。

- 請確定這些電話號碼上沒有啟用進位的通話控制功能，例如通話搜尋、特殊響鈴。

- 請確定您尚未下任何新的服務訂單，或中斷與目前服務提供者的中斷連接。

- 請確定所有號碼都來自同一個電信電信公司與同一個帳戶。

- 請確定您的服務為使用中。 凍結帳戶可防止帳戶上的電信公司變更。 獲授權變更帳戶的人員必須提交訂單給目前的電信公司，才能移除凍結。 此程式可能需要一到三周的時間，視電信公司不同。

## <a name="related-topics"></a>相關主題

- [您的移轉訂單狀態為何？](port-order-status.md)
- [用於通話方案的各種電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
