---
title: 什麼是移轉訂單？
ms.author: v-lanac
author: lanachin
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
description: 瞭解什麼是埠訂單，以及如何將電話號碼從服務提供者轉移至團隊。
ms.openlocfilehash: 7d92c76c62405efbffaff378b2045195c175d867
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827941"
---
# <a name="whats-a-port-order"></a>什麼是移轉訂單？

如果您目前有電話服務提供者或運營商，而且您已經有電話號碼供使用者或服務使用，您必須建立「*埠順序*」，將這些電話號碼轉移至 Microsoft 團隊。 當您將號碼移過時，您可以將這些電話號碼指派給使用者和服務，例如音訊會議（適用于會議橋接）、自動語音應答及通話佇列。
  
在您將電話號碼移植至團隊之後，Microsoft 會成為您的服務提供者，您可以中斷服務與舊版服務提供者或運營商的連線。

請參閱本文中的資訊，瞭解數位移植的相關資訊。 之後，您應該已準備好建立埠順序並傳送您的電話號碼。 如需逐步指示，請參閱[將電話號碼傳送給團隊](transfer-phone-numbers-to-teams.md)。
  
## <a name="what-countries-or-regions-support-number-porting"></a>哪些國家或地區支援數位移植？

您可以在所有支援的國家或地區中移植或傳送電話號碼，但提交埠順序要求的方式取決於電話號碼來自哪個國家或地區。 如需支援編號移植的國家和地區清單，請參閱[管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。
  
## <a name="what-numbers-can-be-transferred"></a>哪些號碼可以轉移？

 **您可以轉移**
  
一般來說，您可以從支援的提供者轉移任何電話號碼，包括：
  
- 土地線路電話號碼。

- 行動裝置電話號碼，例如用於手機和平板電腦的手機號碼。

    > [!NOTE]
    > 轉移手機號碼僅適用于美國和波多黎各。
  
- 付費電話號碼。

- 免付費電話號碼。

    > [!NOTE]
    > 通用國際 Freephone 號碼（UIFN）無法傳送給我們。 
  
- 服務電話號碼，例如用於會議橋接、自動語音應答等。

- 傳真呼叫號碼，但無法用來進行傳真。 必須指派給使用者。

- 電話供應商（例如 Vonage 或 RingCentral）的 VoIP 電話號碼。

- 商務用 Skype 混合式電話號碼。 如果您想要轉移這些號碼，請以<ptn@microsoft.com>電子郵件傳送給我們。

  **您無法傳送：**
  
    > [!NOTE]
    > 此時，您無法從支援的國家或地區（包括來自 VoIP 電話提供者的電話號碼）中轉移任何不受支援之國家或地區的電話號碼。 如需支援的國家/地區清單，請參閱[音訊會議與通話方案的國家/地區可用性](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
  
- 用於資料連線的電話號碼，例如 DSL 線路或寬頻網際網路連線。

- 專用來傳真的電話號碼。

    如果您的現有專用電話號碼是用來傳送傳真的，您*可以*將這些號碼轉接至小組，但您的傳真服務不會如預期的那樣繼續運作。 [傳真服務] 不提供給小組客戶，即使您有電話系統、國內通話方案或國際通話方案的授權。

    如果您將電話號碼移植至團隊，您可以將此電話號碼指派給組織中的使用者，而不是用來進行傳真。

    > [!NOTE]
    > 在英國，我們目前不支援傳送英國非地理數位，包括區功能變數代碼0843、0844、0845、0870、0871、0872的共用成本數位。
  
## <a name="what-information-do-i-need-to-provide"></a>我需要提供哪些資訊？

您必須擁有目前電信公司的所有帳戶資訊。 您在 [埠順序] 中輸入的資訊，主要是在目前服務提供者的最近帳單或發票中找到。 您也必須知道該帳戶的名稱，以及您想要移植的號碼。
  
## <a name="what-are-full-port-and-partial-port-transfers"></a>什麼是完整埠和部分埠傳輸？

當您將電話號碼移植至團隊時，您可以選擇轉移所有號碼或其中的一部分。
  
- **全埠**當您將所有數位從目前的服務提供者轉移至團隊時，就是這種情況。 當您要求您要傳送的電話號碼時，您*必須包含*帳單電話號碼（BTN），以及您帳戶上的所有其他電話號碼。

    例如，假設您的 BTN 是 *+ 1 425-555-1234* ，而且您想要將25個電話號碼（*+ 1 425-555-1235 到 1259*）全部移植。 當您遵循下列指示來轉接您的數位時，請輸入： **+ 14255551234-+ 14255551259**。

- **部分埠**這就是當您只將來自目前服務提供者的一些電話號碼傳送給團隊時。 當您想要將部分電話號碼捆綁到同一個 BTN 時，您 * **不得包含** * 與您帳戶上的其他電話號碼搭配的 BTN。

    例如，假設您的 BTN 是 *+ 1 425-555-1234* ，而您想要移植25個電話號碼中的5個（*+ 1 425-555-1235 至 1259*）。 當您遵循下列指示來轉接您的數位時，請輸入： **+ 1 425 555 1235-+ 1 425 555 1239**。
    
## <a name="can-i-submit-a-single-number-porting-request-for-all-of-my-numbers-at-one-time"></a>我可以一次為所有號碼提交一個數位移植要求嗎？
<a name="bkmk_type_1"> </a>

要移植的每個載波和編號類型，都需要唯一的要求。
  
例如，您需要針對下列每個號碼類型提交唯一的號碼移植要求：
  
- 當地付費電話號碼，也稱為訂閱者號碼或地理位置號碼

- 含區號的免費電話號碼：800、844、855、866、877和888

- 行動電話號碼

- 可在 Office 365 中用來進行音訊會議的服務號碼。

以下是如何針對每種類型的號碼提交編號移植要求的詳細資訊：
  
- 不同的運營商所提供的**電話號碼**，對於每個運營商而言，都需要有唯一的號碼移植要求。

- 含區號（例如：800、844、855、866、877和888）的**免付費電話號碼**，不能包含其他類型的數位移植要求。 若要移植這些免付費電話號碼，您必須[手動提交一個埠順序](manually-submit-port-order.md)。 您無法將這些號碼移植至 Microsoft 團隊系統管理中心。 如需詳細資訊，請參閱[管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

    請務必針對您想要移植的國家/地區和電話號碼類型使用正確的授權字母（LOA）。 您可以[在這裡下載所需的 LOA](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

- **行動電話號碼**需要 PIN 碼來授權轉接。 因此，它們需要個別的數位移植要求。

- **服務編號**移植要求必須自行提交。 它們無法與其他類型的數位一起提交。

## <a name="how-long-does-it-take-to-port-numbers"></a>埠號碼需要多少時間？
<a name="bkmk_type_1"> </a>

完成埠訂單要求之後，會在7-14 天前處理。 不過，視您的服務提供者而定，可能需要長達30天的時間。 在撥出電話號碼之後，您會收到一封電子郵件給我們，讓您可以開始使用。
  
若要檢查您的埠順序狀態，請在 Microsoft 團隊系統管理中心的左導覽中，移至 [**語音** > **電話號碼**]，然後按一下 [**訂購歷程記錄**]。 每個埠訂單狀態都列在 [**狀態**] 欄中。
  
## <a name="can-user-subscriber-phone-numbers-be-converted-to-service-numbers"></a>使用者（訂閱者）電話號碼可以轉換為服務號碼嗎？
<a name="bkmk_type_1"> </a>

可以。 您只需要提交服務要求，其中包含您組織的租使用者 GUID 和您想要轉換的電話號碼。 若要這樣做，請參閱[管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)。

## <a name="common-mistakes-to-watch-out-for"></a>需要注意的常見錯誤
<a name="bkmk_type_1"> </a>

數位移植很容易完成。 您的訂單可以向上 messed，不過，如果電話服務提供者有問題，順序就不完整且遺失資訊，或發生錯誤。
  
以下是我們在客戶撥打電話號碼時最常看到的錯誤。 自行儲存來電給客戶支援，並仔細檢查這些錯誤。
  
- 請確定您所提供的帳戶資訊，與您的電話聯絡人記錄的內容完全相符。 不匹配的資訊是錯誤最常見的原因，而且會延遲您的埠順序。 確認下列專案成立：

  - 已獲授權對帳戶進行變更的名稱或人員是正確的。

  - 位址正確無誤。

  - 帳戶號碼正確無誤。

  - BTN 正確無誤。

- 確認沒有任何高級通話控制功能（例如，在這些電話號碼上啟用 [通話查尋]、[獨特鈴聲]）。

- 確認您還沒有加入任何新的服務訂單，或中斷與目前服務提供者的連線。

- 確定所有號碼都來自同一個承運人和同一個帳戶。

- 請確定您的服務處於作用中狀態。 凍結帳戶會防止帳戶上的載波變更。 獲授權對帳戶進行變更的人員，必須將訂單提交給目前的運營商，才能移除凍結。 這個程式可能需要一到三周的時間，視運營商而定。

## <a name="related-topics"></a>相關主題

- [您的移轉訂單狀態為何？](port-order-status.md)
- [通話方案所用的不同類型的電話號碼](../different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [管理貴組織的電話號碼](../manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [緊急通話條款及條件](../emergency-calling-terms-and-conditions.md)
- [緊急通話免責聲明標籤](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)