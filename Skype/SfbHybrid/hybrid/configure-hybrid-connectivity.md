---
title: 設定混合式連接 |部署商務用 Skype Server 2019 連接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在商務用 Skype Server 和 Teams 之間實施混合式連線的指示。
ms.openlocfilehash: fee7587c641f2fd55cd8b4ac4da72b3944b819a1
ms.sourcegitcommit: 64b9f7297d33a883506893fb68d1ad5202b4df1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2021
ms.locfileid: "59682808"
---
# <a name="configure-hybrid-connectivity-between-skype-for-business-server-and-teams"></a>設定商務用 Skype Server 和 Teams 之間的混合式連線

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

**摘要：** 閱讀此主題以瞭解如何設定商務用 Skype Server 和 Teams 之間的混合式連線。  混合式連線功能可讓您將內部部署使用者移至 Teams，並讓您的使用者能夠充分利用雲端服務。
  
在執行本主題中的步驟之前，您應該具備[商務用 Skype Server 和 Teams 之間](plan-hybrid-connectivity.md)的「讀取計畫」混合式連線。
  
下表列出設定商務用 Skype 混合式連線所需的工作，並提供相關文章的連結以取得詳細資訊。
  
|步驟|描述|
|:-----|:-----|
|建立 Microsoft 365 的租用戶帳戶。   <br/> |深入瞭解 Microsoft 365 [Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)。  <br/> 若要確定您的環境已準備好 Microsoft 365，請參閱[系統需求](https://products.office.com/office-system-requirements)。  <br/> 如需設定 Microsoft 365 的詳細資訊，請參閱[開始使用 Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=254982)。  <br/> |
|將您的網域新增至您的 Microsoft 365 組織，並確認擁有權。  <br/> | 您必須將您的網域新增至您的 Microsoft 365 組織，然後依照步驟使用 Microsoft 365 驗證網域。 這項驗證是為了確認您是網域的擁有者。 <br/> 若要將您的網域新增至您的 Microsoft 365 組織，請依照在[Microsoft 365 新增網域](https://support.office.com/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)中所述的步驟進行。 請務必參閱下列與 [混合式組織之 DNS 含意](#dns-implications-for-on-premises-organizations-that-become-hybrid)相關的指導方針。 <br/> |
|設定 Active Directory 同步處理。  <br/> |Active directory 同步處理可確保您的內部部署 Active Directory 與 Microsoft 365 持續同步，因此您可以為每個使用者帳戶和群組建立同步處理的版本。  <br/> <br> **重要：** 您必須在內部部署與線上部署之間同步處理組織中所有商務用 Skype 使用者的 Active Directory 帳戶，即使使用者未移至 Teams。 如果您未同步處理所有使用者，組織中內部部署與線上使用者之間的通訊可能無法如預期的方式運作。 如需詳細資訊，請參閱[設定混合式環境的 AZURE AD 連線](configure-azure-ad-connect.md)。         |
| 設定商務用 Skype 混合式。 | 有三個基本步驟： <br><br> 1. 設定您的內部部署環境，以與 Microsoft 365 同盟。 <br> 2. 設定您的內部部署環境，以信任 Microsoft 365，並使用 Microsoft 365 啟用共用 SIP 位址空間。<br> 3. 在 Microsoft 365 組織中啟用共用 SIP 位址空間。 <br><br> 此外，如果您有 Exchange 內部部署，您可能想要設定 Exchange 內部部署和線上環境之間的 OAuth。 <br> <br>如需詳細資訊，請參閱[Configure 商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)。
|移動試驗使用者。  <br/> |完成準備及設定環境 Teams 的步驟之後，您可以開始將試驗使用者移至您的線上 Microsoft 365 組織。 如需詳細資訊，請參閱[將使用者從內部部署移至 Teams](move-users-from-on-premises-to-Teams.md)。  <br/> |


## <a name="dns-implications-for-on-premises-organizations-that-become-hybrid"></a>成為混合式之內部部署組織的 DNS 含意

承租人預設會建立為 TeamsOnly 模式。 管理員無法變更此設定。 不過，混合式組織一定不能是 TeamsOnly 模式，因為這會中斷其內部部署使用者的同盟。 Teams 具有內建機制，以確保不會對新的混合承租人套用租使用者的 TeamsOnly 設定，同時也會 *從成為混合式的現有承租人中移除* 租使用者範圍的 TeamsOnly 設定。 此機制是根據任何已驗證 Microsoft 365 網域 (的 LyncDiscover DNS 記錄值而定，因為在大多數情況下，商務用 Skype Server 內部部署會將該記錄) ，如下所述。

初次處理新的 Microsoft 365 訂閱時，會發生下列情況：
- 如果尚未驗證 Microsoft 365 網域，則會建立租使用者為 TeamsOnly 模式。 該值是透過 TeamsUpgradeOverridePolicy 進行設定，而這只可由 Microsoft 設定。 如果原則值為 UpgradeToTeams，則其優先順序會高於任何 TeamsUpgradePolicy 的值。
- 如果已驗證 Microsoft 365 網域，但未偵測到任何公用 DNS LyncDiscover 記錄，或任何已偵測到 Microsoft 365 (sipfed.online.lync.com、sipfed.online.gov.skypeforbusiness.us) 等的任何 LyncDiscover 記錄，則租使用者會透過 TeamsOnly (建立 TeamsUpgradeOverridePolicy 模式) 。
- 如果至少有一個已驗證的 Microsoft 365 網域會偵測 LyncDiscover 記錄，而該記錄指向 Microsoft 365 以外的位置，則租使用者建立為孤島模式。

重新布建現有的 Microsoft 365 租使用者時 (通常是因為變更已驗證的網域或訂閱詳細資料) 中的變更，則會發生下列情況：
- 如果找到一或多個 Microsoft 365 驗證的網域的 LyncDiscover 記錄，而該記錄未指向 Microsoft 365 時，則會移除以整個 TeamsUpgradeOverridePolicy)  (的租使用者 TeamsOnly 模式。 租使用者模式會還原為 TeamsUpgradePolicy 的承租人層級所指定的內容，預設為孤島模式。


這種自動偵測機制有一些限制：
- 如果您的組織沒有任何公用 DNS 記錄，TeamsOnly 模式將不會被移除，因為 Microsoft 365 將無法偵測記錄。 如果您的組織具有內部部署商務用 Skype Server 但沒有公用 DNS 專案，您必須聯繫 Microsoft 支援部門以降級租使用者。
- 如果您新增/更新公用 DNS 記錄至 *已* Microsoft 365 驗證的網域的網域，將不會偵測到 DNS 變更，也不會移除 TeamsOnly 模式。 TeamsOnly 模式只會在租使用者重新布建時移除，這通常會在變更 Microsoft 365 驗證的網域或訂閱時發生。  
