---
title: 什麼是移轉訂單？
author: CarolynRowe
ms.author: crowe
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
description: 概略瞭解什麼是移轉訂單，以及如何將電話號碼從服務提供者移轉到 Teams。
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.openlocfilehash: f4160d8e5fac5ec1f706bb7c82a881248d092a59
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584914"
---
# <a name="whats-a-port-order"></a>什麼是移轉訂單？

如果您目前已有電話服務提供者或電信業者，而且已經有使用者或服務的電話號碼，您必須建立「*移轉訂單*」，將這些電話號碼移轉到 Microsoft Teams。 移轉號碼之後，您可以將這些電話號碼指派給您的使用者和服務，例如會議橋接器) 的音訊會議 (、自動語音應答，以及通話佇列。
  
將電話號碼移轉到 Teams 之後，Microsoft 就會成為您的服務提供者，您可以中斷與舊服務提供者或電信業者的服務。

請檢閱本文中的資訊，熟悉號碼移轉。 之後，您應該可以建立移轉訂單並移轉電話號碼。 如需逐步指示，請參閱 [將電話號碼移轉到 Teams](transfer-phone-numbers-to-teams.md) 。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些國家或地區支援號碼移轉？

您可以在所有支援的國家或地區中移轉電話號碼，但您提交移轉訂單要求的方式取決於電話號碼的來源國家或地區。 如需支援號碼移轉的國家與地區清單，請參閱 [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。  

目前，Microsoft Teams 系統管理中心的[移轉精靈](transfer-phone-numbers-to-teams.md)支援取得英國、Estados Unidos和加拿大的電話號碼。 若要取得其他國家/地區的電話號碼，您可以 [手動提交移轉訂單](manually-submit-port-order.md)。
  
## <a name="what-numbers-can-be-transferred"></a>可以轉移哪些數位？

 **您可以移轉**
  
一般說來，您可以從支援的提供者移轉任何電話號碼，包括：
  
- 有線電話號碼。

- 行動電話與平板電腦所用的行動裝置電話號碼。

    > [!NOTE]
    > 移轉行動電話號碼僅適用于Estados Unidos和波多黎各。
  
- 付費電話號碼。

- 免付費電話號碼。

    > [!NOTE]
    > 通用國際免費電話號碼 (UIFN) 無法傳輸給我們。
    > 免付費電話號碼的移轉可用性可能會因國家/地區而異。 若要尋找我們的詳細資訊，請參閱您的國家或地區特定檔，以查看移轉服務的可用支援。 
  
- 服務電話號碼，例如會議橋、自動語音應答等所用的服務電話號碼。

- 傳真呼叫號碼，但無法用來傳真。 他們必須指派給使用者。

- 來自電話提供者（例如 Vonage 或 RingCentral）的 VoIP 電話號碼。

- 如果您要移轉混合式電話號碼 (從直接路由或運算子連線到通話方案移轉) 請連絡 [電話號碼服務小組](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)，請確定您附上說明這些是混合式電話號碼的附注。

**您無法移轉：**
  
> [!NOTE]
> 目前，您無法移轉來自受支援國家或地區的任何電話號碼或號碼，包括來自 VoIP 電話提供者的電話號碼。 如需支援的國家/地區清單，請參閱 [音訊會議和通話方案的國家/地區可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 用於資料連線的電話號碼，例如 DSL 線路或寬頻網際網路連線。

- 傳真專用的電話號碼。

    如果您有用於傳真的現有專用電話號碼，  *您可以*  將這些號碼移轉到 Teams，但傳真服務將無法繼續如預期般運作。 即使您擁有電話系統、國內通話方案或國際通話方案的授權，Teams 客戶也無法使用傳真服務。

    如果您將電話號碼移轉至 Teams，您可以將這個電話號碼指派給組織中的使用者，而不是用來傳真。

> [!NOTE]
> 目前在英國，我們目前不支援移轉英國非地理位置號碼，包括區碼 0843、0844、0845、0870、0871、0872 的共用成本數位。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些資訊？

您必須擁有目前電信業者的所有帳戶資訊。 您在移轉訂單中輸入的資訊大多位於您目前服務提供者的最新帳單或發票上。 您也必須知道帳戶上有誰的名稱，以及您想要移轉的號碼。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什麼是全埠和部分埠傳輸？

當您將電話號碼移轉到 Teams 時，您可以選擇移轉所有號碼或其中一部分。
  
- **完整埠** 這是當您將所有號碼從目前的服務提供者移轉到 Teams 時。 當系統要求您移轉的電話號碼時，您 *必須包含* 帳單電話號碼 (BTN) 以及帳戶中所有其他電話號碼。

    例如，假設您的 BTN  *是 +1 425-555-1234*  ，而您想要將 25 個電話號碼全部移轉 (*+1 425-555-1235 到 1259*) 。 當您依照下列指示移轉您的號碼時，您會輸入： **+14255551234 - +14255551259**。

- **部分埠** 這是當您只將部分電話號碼從目前的服務提供者移轉至 Teams 時。 當您想要移轉一些系結到相同 BTN 的電話號碼時，您 ** *不能將* ** BTN 連同您帳戶上所有其他的電話號碼一起包含。

    例如，假設您的 BTN  *是 +1 425-555-1234*  ，而您只想要移轉 25 個電話號碼中的 5 個， (*+1 425-555-1235 到 1259*) 。 當您依照下列指示傳輸號碼時，會輸入： **+1 425 555 1235 - +1 425 555 1239**。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我可以一次為我所有的號碼提交單一號碼移轉要求嗎？
<a name="bkmk_type_1"> </a>

每個電信業者及要移轉的號碼類型都需要唯一的要求。
  
例如，您必須針對下列每種類型的數位提交唯一號碼移轉要求：
  
- 當地付費電話號碼，也稱為訂閱者號碼或地理號碼

- 含區碼的免付費號碼，例如：800、844、855、866、877 和 888

- 行動電話號碼

- Microsoft 365 或 Office 365 中可用於音訊會議的服務號碼。

以下提供有關如何針對每一種類型的數位提交號碼移轉要求的詳細資訊：
  
- 不同電信業者所提供的 **電話號碼** 需要針對每個電信業者的號碼提供唯一的移轉要求。

- 包含區碼的 **免付費號碼**，例如：800、844、855、866、877 和 888 等號碼無法包含在號碼移轉要求與其他類型的號碼中。 若要移轉這些免付費電話號碼，您必須 [手動提交移轉訂單](manually-submit-port-order.md)。 您無法在 Microsoft Teams 系統管理中心移轉這些數位。 如需詳細資訊，請參閱 [管理組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    請務必針對國家/地區使用正確的授權委託書 (LOA) ，以及您要移轉的電話號碼類型。 您可以 [在這裡下載所需的 LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- **行動電話號碼** 需要 PIN 碼才能授權傳輸。 因此，他們需要個別的號碼移轉要求。

- 必須自行提交 **服務號碼** 移轉要求。 無法以其他類型的數位提交。

## <a name="how-long-does-it-take-to-port-numbers"></a>移轉號碼需要多久時間？
<a name="bkmk_type_1"> </a>

完成移轉訂單要求之後，需要 7-14 天才能處理。 不過，視您的服務提供者而定，最多可能需要 30 天。 移轉電話號碼之後，您會收到我們寄來的電子郵件，讓您知道您已準備就緒。
  
若要檢查移轉訂單的狀態，請在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[語音**  >  **電話號碼]**，然後按一下 [**訂購記錄]**。 每個移轉訂單狀態都會列在 **[狀態** ] 欄中。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>使用者 (使用者) 電話號碼是否可以轉換為服務號碼？
<a name="bkmk_type_1"> </a>

是的，他們可以。 若要這麼做，請參閱 [管理電話號碼的使用方式](../manage-the-usage-of-a-phone-number.md)。

## <a name="can-i-port-out-my-numbers-from-teams-to-a-different-phone-service-provider-or-carrier"></a>我可以將我的號碼從 Teams 移轉到其他電話服務提供者或電信業者嗎？

若要將您的號碼從 Teams 移轉到不同的電信業者，您必須向新的電信業者提交要求。 您也需要在 Microsoft Teams 系統管理中心設定移轉 PIN。

若要定義您的移轉 PIN 碼，請在 Microsoft Teams 系統管理中心的左側導覽中，移至頁面右上角的 **[語音**  >  **電話號碼**]，選取 **[管理移轉 PIN]**，然後輸入 10 位數 PIN。

當您的新電信業者連絡我們提出移轉要求時，我們會要求他們提供您定義的 PIN。

如果您需要進一步設定 PIN 的異動性，請連絡 [電話號碼服務小組](../manage-phone-numbers-for-your-organization/contact-tns-service-desk.md)

## <a name="common-mistakes-to-watch-out-for"></a>需要注意的常見錯誤
<a name="bkmk_type_1"> </a>

號碼移轉很簡單。 不過，如果電話服務提供者發生問題、訂單不完整且缺少資訊，或是有錯字，您的訂單可能會被打亂。
  
以下是客戶在移轉號碼時所犯的最常見錯誤。 向客戶支援人員撥打電話給自己，並再次檢查這些錯誤。
  
- 請確定您所提供之帳戶資訊完全符合您的電信業者記錄中的帳戶資訊。 不相符的資訊是移轉訂單發生錯誤和延遲的最常見原因。 確認下列為 True：

  - 有權變更帳戶的名稱或人員是正確的。

  - 位址正確無誤。

  - 帳戶號碼正確無誤。

  - BTN 正確無誤。

- 確定這些電話號碼上沒有啟用進階通話控制功能，例如通話搜尋、特殊撥打。

- 請確定您尚未下任何新的服務訂單，或中斷與您目前服務提供者的連線。

- 確定所有號碼都來自同一個電信業者和相同的帳戶。

- 確定您的服務為使用中狀態。 凍結帳戶可防止帳戶上的電信業者變更。 獲授權變更帳戶的人員必須提交訂單給目前的電信業者，才能移除凍結。 視電信業者而定，此程式可能需要一到三周的時間。

## <a name="related-topics"></a>相關主題

- [您的移轉訂單狀態為何？](port-order-status.md)
- [通話方案所用的不同電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
