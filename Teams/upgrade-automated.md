---
title: 自動升級 |商務用 Skype 企業對團隊升級
author: serdarsoysal
ms.author: billkau
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 從商務用 Skype 自動升級至團隊的概覽
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4f6e994f41f44c2895d394b432b37bed617ad2eb
ms.sourcegitcommit: 70323d648e9ae3b20a710120b9dcdc452afc462b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/24/2019
ms.locfileid: "37698048"
---
# <a name="automated-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>從商務用 Skype Online 到 Microsoft 團隊的自動升級

Microsoft 將自動升級提供給小組，以協助小型企業從商務用 Skype Online 到2021停用的服務之前，進行成功的轉換。 自動升級減少了客戶所需的技術工作，並可讓您更注重組織的準備、使用者意識及小組訓練。

從商務用 Skype 升級到 Microsoft 小組的成功，需要規劃技術與使用者的準備情況。 當您準備好開始使用時，Microsoft 會提供[升級行動方案](upgrade-basic.md)，其中含核心建議的活動和相關資源，可讓您從商務用 Skype 成功移至團隊。

## <a name="notifications-for-scheduled-customers"></a>針對排程客戶的通知

符合自動升級至小組資格的商務用 Skype Online 客戶，將會在排程升級日期前的30天內收到一系列升級通知。 這些通知將會在系統管理訊息中心中傳送為變更文章的*計畫*，將電子郵件升級至全域系統管理員，並將 app 內標誌升級至最終使用者。

這些通知將會傳達自動升級的排程日期，將連結到升級資源和訓練，以協助推動小組的使用及使用量，並讓客戶能選擇將自己的自動升級延遲到事件未準備好透過其排程日期進行升級。

## <a name="the-automated-upgrade-experience"></a>自動升級體驗

自動升級會在他們的排程升級日期執行，在通知電子郵件、訊息中心，以及團隊管理入口網站中進行通訊。 完成升級大約需要15分鐘，在此期間使用者仍可存取商務用 Skype Online 功能。 升級完成後，使用者登出商務用 Skype Online 後，使用者將只能使用小組進行訊息、會議和通話。

## <a name="the-post-upgrade-experience"></a>升級後的體驗

當您的自動升級完成時，**共存模式**會設定為 [僅限團隊]，而且只能透過 Microsoft 將其變更為其他共存模式。 在升級前，系統管理員應該[只審查小組的模式考慮](teams-only-mode-considerations.md)。 下表提供團隊只有使用者體驗的高層次概覽。


|  |  |
|---------|---------|
|**聊天與通話**     | <UL><LI>所有通話和聊天都是在小組中開始和接收<LI>使用者可以使用任何商務用 Skype 使用者進行交互操作（聊天/通話）<LI>使用者無法與使用客戶用 Skype 的使用者通訊<LI>如果使用者嘗試登入商務用 Skype，就會將他們重新導向至團隊      </UL>  |
|**舉行**     |  <UL><LI>使用者排程小組中的所有新會議（已取代外掛程式）    </UL>   |
|**已遷移的資料**     |<UL><LI>商務用 Skype 中的現有連絡人，包括同盟（但不含通訊群組清單）<LI>現有的商務用 Skype 會議（無論是內部部署還是線上）都能轉換成團隊會議</UL>         |

## <a name="postponing-your-automated-upgrade"></a>推遲您的自動升級

從商務用 Skype Online 到 Microsoft 團隊的成功轉場需要技術規劃與使用者準備，以確保貴組織充分利用延伸的功能和小組效能。 不過，當您規劃升級時，您可能會發現貴組織目前尚未準備好升級至小組。

如果您收到有關排程的自動升級至小組的通知，且想要推遲到較晚的日期，Office 365 全域系統管理員可能會登入團隊管理入口網站，然後按一下 [*延遲*] 按鈕。 這麼做會將自動升級日期推出30天。 當您在延遲後重新整理團隊管理入口網站時，您會看到包含新的自動升級日期的通知。

## <a name="requests-to-downgrade-to-skype-for-business"></a>降級至商務用 Skype 的要求

我們允許從團隊到 SfBO 的一次性降級，以允許租使用者進一步準備其升級至小組。 已降級的租使用者將會重新參與自動升級60天，從其降級日期開始。

## <a name="related-content"></a>相關內容

- [Microsoft 團隊升級快速入門](upgrade-start-here.md)
- [終止對商務用 Skype Online 的支援](skype-for-business-online-retirement.md)
- [CsTeamsUpgradeStatus](https://docs.microsoft.com/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps)
- [僅限團隊的模式考慮](teams-only-mode-considerations.md)

