---
title: 在 Teams 中管理第一線試用版
author: daisyfell
ms.author: daisyfeller
ms.reviewer: samanro
manager: pamgreen
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何為組織試用第一線員工設定 90 天Teams。
ms.localizationpriority: medium
ms.collection:
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 098cb4cd84616a9b26ea7df5c1451219fd5b5f0e
ms.sourcegitcommit: 8ce73ea99be607f5cdccb22a5366bc96e8fb09c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/27/2022
ms.locfileid: "65758292"
---
# <a name="manage-the-frontline-trial-in-teams"></a>在 Teams 中管理第一線試用版

> [!NOTE]
> 此試用體驗即將推出。 您可以在Microsoft 365 系統管理[中心的 [訊息中心](https://go.microsoft.com/fwlink/p/?linkid=2070717)] 中尋找訊息，以檢查組織何時可以使用此功能。

Microsoft Teams第一線試用版體驗可讓組織中Teams的使用者為整個前線小組起始Teams體驗，只要其他成員在 Azure Active Directory (Azure AD) 。 您可以使用 [AllowSelfServicePurchase PowerShell 模組](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)，針對組織中的使用者停用這項功能。

## <a name="what-services-are-included"></a>包含哪些服務

試用版包含[Microsoft 365 F3授權](https://www.microsoft.com/microsoft-365/enterprise/f3)中的所有專案，但有下列例外狀況：

- 第一線試用版包含Exchange Foundation，而非Exchange Kiosk。 使用者可能會因為此變更而遺失其他Teams功能。

## <a name="eligibility"></a>資格

> [!NOTE]
> 您可以在Microsoft 365 系統管理[中心的訊息中心](https://go.microsoft.com/fwlink/p/?linkid=2070717)中尋找公告，來檢查貴組織是否為試用試驗的一部分。 您的組織必須是試用試驗的一部分，使用者才能啟動或參與試用版。 此方案不適用 GCC、GCC High、DoD 或教育版客戶。

「第一線試用版」每個試用版最多可容納 300 個使用者。

如果使用者可以啟動小組的第一線試用版：：

- 擁有可讓他們存取Teams的使用中授權。
- 先前尚未開始一線員工試用。

> [!IMPORTANT]
> 如果啟動試用版的使用者在試用版結束之前離開貴組織，您身為系統管理員將需要監控試用版，請洽詢團隊以查看誰受益于這些功能，並決定您需要升級至付費授權的使用者。

如果使用者擁有受管理Azure Active Directory網域電子郵件地址，就可以參與第一線員工試用版。

如果使用者先前已開始試用，但無法啟動另一個試用版，則可以參與。

> [!NOTE]
> 沒有現有Teams存取權的使用者，只能在建立團隊時新增至試用團隊。 現有Teams建立團隊之後，仍然可以將使用者新增至試用版。

## <a name="set-up-the-trial"></a>設定試用版

符合資格的使用者可以從桌面或 Web 應用程式登入Teams中的工作應用程式，以啟動「第一線試用[版」](https://teams.microsoft.com/_#/apps/com.microsoft.teamspace.tab.planner/sections/mytasks)。 目前不支援透過行動裝置啟動第一線試用版。 啟動試用版時，系統會自動指派整個小組的「前線試用版」授權。 擁有現有付費授權並讓他們存取Teams的使用者，也會被指派試用版授權，但在整個試用版期間仍將維持其現有授權的功能，並在試用期結束後保留現有的付費授權。 開始試用版的使用者會在整個試用期間收到電子郵件通知。

## <a name="manage-the-frontline-trials-experience"></a>管理第一線試用版體驗

系統管理員可以使用 **AllowSelfServicePurchase** PowerShell 模組，防止使用者在其組織內啟動第一線試用版。 這僅適用于試用版授權。 [瞭解如何使用 AllowSelfServicePurchase PowerShell 模組](/microsoft-365/commerce/subscriptions/allowselfservicepurchase-powershell)。

### <a name="manage-teams-for-users-who-have-the-frontline-trial-license"></a>管理擁有第一線試用版授權之使用者的Teams

您可以管理擁有第一線試用版授權的使用者，就像管理擁有一般付費授權的使用者一樣。 如需詳細資訊，請參閱[管理貴組織的 Teams 設定](/microsoftteams/manage-teams-overview)。

### <a name="remove-a-trial-license"></a>移除試用版授權

您可以透過 PowerShell 或您的Microsoft 365 系統管理中心移除「第一線試用版」授權。

[瞭解如何使用 PowerShell 移除](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)。

[瞭解如何在系統管理中心移除](/microsoft-365/admin/add-users/delete-a-user)。

## <a name="upgrade-users-from-frontline-trial"></a>從第一線試用版升級使用者

使用者可能會在試用期結束後與您連絡以要求授權。 您需要系統管理員許可權才能升級您的使用者。

### <a name="when-to-upgrade"></a>升級時間

90 天試用期即將結束，您必須洽詢您的使用者，以查看誰需要繼續使用付費授權。 請務必在 [第一線試用版] 訂閱到期前執行此動作，以避免對使用者體驗造成任何干擾。

> [!IMPORTANT]
> 如果第一線試用版授權結束，且使用者未立即指派包含Teams的授權，他們就會失去Teams的存取權。 30 天后，系統會刪除其資料 (檔案、郵件及其他) 。 使用者仍然存在於 Azure Active Directory 中。 如果在 30 天內指派新授權給使用者以啟用Teams功能，Teams中的所有內容仍會存在。

### <a name="choose-an-upgrade-path"></a>選擇升級路徑

> [!TIP]
> 「第一線試用版」是以[Microsoft 365 F3授權](https://www.microsoft.com/microsoft-365/enterprise/f3)為基礎。

視貴組織目前擁有的訂閱而定，有三種方式可以從一線試用版升級為付費授權：

- **升級現有的 Microsoft 365 訂閱。** 如果您的組織擁有其他不包含 Teams 的 Office 產品訂閱，請使用此選項。 如需詳細資訊，請參閱 [升級至其他方案](/microsoft-365/commerce/subscriptions/upgrade-to-different-plan)。 若要查看現有訂閱的作用中使用者，請移至 Microsoft 365 系統管理中心 **使用者 >** [作用中使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)。

- **新增使用者至現有的 Microsoft 365 訂閱。** 如果貴組織沒有足夠的付費Teams授權來涵蓋前線小組，請使用此選項。 如需詳細資訊，請參閱 [購買或移除授權](/microsoft-365/commerce/licenses/buy-licenses)。 若要新增使用者至已擁有足夠可用授權的現有訂閱，請參閱 [將使用者移至不同的訂閱](/microsoft-365/commerce/subscriptions/move-users-different-subscription)。 若要查看現有訂閱的作用中使用者，請移至 Microsoft 365 系統管理中心 **使用者 >** [作用中使用者](https://go.microsoft.com/fwlink/p/?linkid=834822)。

- **購買新的 Microsoft 365 訂閱。** 如果貴組織沒有任何現有的Office產品訂閱，或如果您的組織想要購買與其現有訂閱不同的訂閱，以涵蓋前線使用者，請使用此選項。 如需詳細資訊，請[參閱Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline)。

如果您不確定要升級哪Microsoft 365訂閱，請參[閱Microsoft 365 for frontline workers](https://www.microsoft.com/microsoft-365/enterprise/frontline)。 如果您在選擇訂閱時需要額外的協助，或如果您的組織需要超過 300 份授權，請聯絡您的 [Microsoft 合作夥伴](https://www.microsoft.com/solution-providers/home) 或 Microsoft 帳戶代表。

### <a name="assign-paid-licenses"></a>指派付費授權

若要指派您新取得的授權，請參閱 [指派授權給使用者](/microsoft-365/admin/manage/assign-licenses-to-users)。  

指派新授權之後，請取消指派 Teams Exploratory 授權。 請參閱 [由使用者取消指派授權](/microsoft-365/admin/manage/remove-licenses-from-users)，以取得詳細資訊。

## <a name="faq"></a>常見問題集

**試用期持續多久** <br>
第一線試用會持續 90 天。

**系統管理員在 90 天第一線試用版體驗結束時應該做什麼？** <br>
在 90 天試用期結束時，您必須洽詢您的使用者，以查看誰需要繼續使用付費授權。 然後您將需要 [升級您的使用者](#upgrade-users-from-frontline-trial)。

**如果試用版的使用者離開貴組織，會發生什麼情況？** <br>
身為系統管理員的您將需要監控 90 天期間剩餘時間的試用版，並在試用期結束時升級為需要的使用者付費授權。

**什麼是資料保留原則？** <br>
您可以從Microsoft 365[訂閱資訊](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?)瞭解資料保留。

**如果使用者在啟動第一線試用版時遇到錯誤，該怎麼辦？** <br>
請確定您的組織、開始試用的使用者以及新增至試用版的使用者符合 [資格準則](#eligibility)。