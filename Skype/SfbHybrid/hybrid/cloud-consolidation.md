---
title: 針對小組與 Skype for Business 的雲端彙總
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文說明如何達到該合併為組織內部 deployment(s) 的 Skype for Business （或 Lync） 正在尋找將移至移動給小組其 UC 工作負載和/或商務用 Skype。
ms.openlocfilehash: 7f3ad27404ec80e0592baa7174b01363f1aa0ed1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726953"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams 和商務用 Skype 的雲端整合

許多大型企業擁有多個內部部署 AD 樹系，在某些情況下，客戶會有多個 Exchange 和/或商務用 Skype Server (或 Lync Server) 部署。 此外，即使是只有一個內部部署樹系的組織，透過企業併購的過程，也會發現自己處於類似的情況。 當這些客戶移至雲端時，可以將特定內部部署工作負載的多個執行個體合併到雲端的單一 Office 365 租用戶。 本文說明如何達到該合併彙算的 Skype for Business （或 Lync） 給想要將其 UC 工作量移至 Microsoft 雲端，例如、 Microsoft Teams 和/或商務用 Skype 與多個內部部署組織。

針對這類狀況的客戶，過去的指導方針是先合併內部部署的部署，然後再移至雲端。 雖然這仍然是一個選項，這篇文章說明根據新功能可讓組織具有多個 Skype for Business 部署移轉到單一 Office 365 租用戶，一次一個部署不需再做為內部的解決方案彙總。 請注意，即使有這項新功能，Skype for Business Online 和 Microsoft Teams 不支援多個 Skype for Business/Lync 樹系中使用單一 Office 365 租用戶混合模式。 

> [!Important]
> 之前使用本指南的設定，請確定已閱讀並瞭解[限制](#limitations)，因為它們可能會影響您的組織。

## <a name="overview-of-cloud-consolidation"></a>雲端整合概述

只要符合下列關鍵需求，任何擁有多個商務用 Skype 部署的組織，都能將內部部署的所有使用者合併到雲端的單一 Office 365 租用戶中：

- 最多只能有一個 Office 365 租用戶。 不支援多個 Office 365 租用戶案例的合併。
- 任何時候，只有一個內部部署商務用 Skype 樹系可以處於混合模式 (共用 SIP 位址空間)。 其他所有內部部署商務用 Skype 樹系都必須仍是內部部署 (而且可能會互相形成同盟)。 請注意，這些其他內部部署組織*可以*同步處理至 AAD 如果想要與[新功能，以停用線上的 SIP 網域](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps)可用截至 2018 年 12 月。

在多個樹系中有多個商務用 Skype 部署的客戶，必須使用共用 SIP 位址空間功能，個別將單一混合式商務用 Skype 樹系的所有使用者，完全移轉到 Office 365 租用戶中，然後停用該內部部署的混合式部署，再繼續移轉下一個內部部署商務用 Skype 部署。 在移轉到雲端之前，內部部署使用者與任何不在相同使用者內部部署目錄中的使用者還是會保持同盟狀態。  

## <a name="canonical-example-of-cloud-consolidation"></a>雲端合併彙算的標準範例

請考慮與想要合併它們線上 Microsoft Teams 中的商務用 Skype 或商務用 Skype 的兩個個別同盟的內部部署組織。


|原始狀態詳細資料 |需要的狀態的詳細資訊 |
|---------|---------|
|<ul><li>2 獨立商務用 Skype 內部部署在不同的 AD 樹系<li>最多 1 的樹系是在混合式架構與 Skype for Business Online <li> 是與彼此同盟組織的 Emc <li>使用者不會在這些樹系之間同步處理<li> 組織可能會有 Office 365 租用戶，可能他們的目錄同步到 Azure AD</ul>|<ul> <li>1 office 365 租用戶<li>沒有其他內部部署，所以沒有剩餘的混合式<li>從內部部署的所有使用者位於商務用 Skype 和 （選用） 可能是僅限小組的使用者 <li>無內部的磁碟使用量商務用 Skype 無所不在 <li>使用者仍有內部部署驗證</ul> |

![合併兩個個別同盟的內部部署](../media/cloudconsolidationfig1.png)  

若要從原來的狀態取得想要的最終狀態的基本步驟如下。  請注意，有些組織可能會發現他們的起點是某處中間這些步驟。 本文稍後，請參閱[其他起始點](#other-starting-points)。 最後，在某些情況下的順序可以調整，視需要而定。 索引鍵條件約束限制說明[及](#limitations)更新版本。

1.  如果沒有尚未存在，請取得 Office 365 租用戶。
2.  請確定所有相關跨兩個內部部署的 SIP 網域已驗證的 Office 365 網域。
3.  選擇一個商務用 Skype 會與 Office 365 的混合式的企業部署。 在這個範例中，我們將使用 OriginalCompany。<span>com。
4.  [啟用 AAD 連線的樹系](configure-azure-ad-connect.md)中第一次將成為混合式 (OriginalCompany。<span>com)。 
5.  如果您將介紹 Teams 進入您的組織，為[TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy) SfBWithTeamsCollab 或下列其中一個其他 SfB 模式 （SfBOnly 或 SfBWithTeamsCollabAndMeetings） 的全租用戶原則。 這是很重要的通話路由傳送，而且聊天室的使用者移至 [僅小組會保留在內部部署的使用者。
6.  它是建議使用這個時候 （但尚未必要步驟 11 之前） 若要[啟用 AAD Connect 為其他樹系](cloud-consolidation-aad-connect.md)(AcquiredCompany。<span>com)。 假設 AAD 連線兩個樹系中已啟用，組織看起來像**[圖](#figure-a)**，這可能是常見的起點的部分組織的 emc。 
7.  針對任何其他內部部署所主控的 SIP 網域 (在此情況下，AcquiredCompany。<span>com)，[停用這些中的 SIP 網域 Skype for Business Online](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)使用`Disable-CsOnlineSipDomain`PowerShell 中。 （這是截至 2018 年 12 月的新功能）。
8.  [設定混合式商務用](configure-federation-with-skype-for-business-online.md)為 OriginalCompany 的。<span>com （一個部署，仍有啟用線上的 SIP 網域）。
9.  混合式部署中 (OriginalCompany。<span>com)，開始[移動使用者從內部部署到雲端的商務用 Skype](move-users-between-on-premises-and-cloud.md) (是否小組僅限與否) 以便帳戶位於 skype for Business Online。 現在組織看起來像**[圖 B](#figure-b)**。圖的重要變更是：
    - 這兩個內部部署目錄中的使用者現在則位於 AAD。
    - AcquiredCompany。<span>com 是已停用線上 SIP 網域。
    - 一些使用者已移線上任一 skype for Business Online 或 microsoft Teams。 （請參閱紫色使用者 a）
10. 一旦所有使用者都移至雲端，OriginalCompany 用的 [[停用與 Skype for Business 的內部部署的混合式](cloud-consolidation-disabling-hybrid.md)。<span>com 的 Office 365:  
    - 在 Office 365 租用戶中停用分割網域。
    - 停用與 Office 365 中 OriginalCompany 通訊的功能。<span>com 內部。
    - OriginalCompany 更新 DNS 記錄。<span>以指向 Office 365 的 com。
11. 如果不這麼做，[啟用 AAD 連線的下一個樹系](cloud-consolidation-aad-connect.md)，將會移混合式 (AcquiredCompany。<span>com)。 此時，組織看起來像**[圖 C](#figure-c)**。這可能是另一個常見的起始點的某些組織。 
12. 在 PowerShell 中[啟用的下一個內部部署的 SIP 網域](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps)，將會移混合式，AcquiredCompany。<span>com。 這是使用`Enable-CsOnlineSipDomain`，也就是截至 2018 年 12 月的可用的新功能。
13. 如果您使用關閉的同盟，您必須新增任何 SIP 網域 (不含 *。 microsoftonline.com) 的純虛擬 online 中的租用戶允許的網域為**同一個**Office 365。 請注意，它可能需要一些時間前變更才會生效，而且沒有無礙早期，這項作業，我們建議這麼做也遲移至步驟 14。
14. 更新以接受從 online 租用戶，任何 SIP 網域，這樣它們符合的內部部署環境。
    - [更新所有 edge 憑證中的 SAN](cloud-consolidation-edge-certificates.md)為相同的值為之前加上的任何現有的線上 SIP 網域值 (除非 *。 microsoftonline.com)、 在此情況下，Sip.OriginalCompany。<span>com。
    - 請確定 OriginalCompany。<span>com 是[允許的網域](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain)在內部部署中，AcquiredCompany。 加入允許的網域。
15. [啟用 Skype for Business 混合式](configure-federation-with-skype-for-business-online.md)內部部署 AcquiredCompany 之間。<span>com 和雲端。
16. 做為所需，[將使用者從內部部署到雲端移轉](move-users-between-on-premises-and-cloud.md)。 您可以將使用者移轉可以直接以[TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability)模式或您可以移轉第一次到 Skype for Business Online。 在此狀態下，期間組織看起來像**[圖 D](#figure-d)**。
17. 一旦移轉所有使用者，讓*組織純雲端*的 [[停用在內部部署環境的混合式](cloud-consolidation-disabling-hybrid.md)！

下列圖表顯示此程序期間各種重點組態。

##### <a name="figure-a"></a>圖答：

- 透過 AAD Connect，AAD 現在有所有的使用者，同時讓兩個組織同步處理內部部署。
- 所有使用者都位於內部部署。  
- Skype 混合式商務*未*尚未設定。
- 如果任一部署中的使用者使用 Teams，他們將無法與其他每] （或任何組織） 聯盟也不會有與商務版使用者任何商務用 Skype 互通性。 在這個階段中，Microsoft 建議只使用 Teams 的通道。<br><br>
    ![圖圖表](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>圖 b:

- AcquiredCompany。<span>com 是[停用](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)線上的 SIP 網域。 所有使用者都是內部部署。 如果他們使用 Teams 他們沒有同盟或互通性。 在這個階段中，Microsoft 建議只使用 Teams 的通道。
- 其中一個內部部署組織已啟用混合式商務用 Skype。
- 混合式組織中的某些使用者已移至雲端 （使用者的紫色網底所指示）。 這些使用者可以是商務用 Skype 商務 Online 使用者，或是只小組使用完整的互通性和同盟支援的使用者。<br><br>
    ![圖 B 圖表](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>圖 c:

- 從 OriginalCompany 的所有使用者。<span>com 皆已在雲端 （位於 Skype for Business Online）。 建議，它們也是僅限 microsoft Teams。
- Skype 商務混合式組態與 OriginalCompany。<span>com 部署已停用。 在內部部署已消失。
- 如果 AcquiredCompany。<span>com 先前未同步處理至 AAD，若要繼續從此處它必須立即同步處理。 但它尚未混合式 （共用 SIP 位址空間），且使線上小組使用者可以與彼此，單純的內部部署組織 (AcquiredCompany.com) 的線上 SIP 網域直到準備好可以移動至混合式部署組織，應保持停用]，在內部部署使用者。<br><br>
    ![圖 C 圖表](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>圖 d:

- AcquiredCompany。<span>com 現已啟用為線上的 SIP 網域。
- 內部部署會更新以接受 OriginalCompany。<span>com。 （同時允許的網域，而且邊緣憑證會更新）。
- 間 AcquiredCompany 已啟用共用 SIP 位址空間。<span>com 和 Office 365 租用戶。
- 混合式組織中的某些使用者可能已移至雲端，例如使用者 D 下方 （紫色網底所指示）。<br><br>
    ![圖 D 圖表](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>其他的起點

在上述範例中正式步驟假設組織開頭具有沒有 Office 365 平台服務的兩個同盟的內部部署。 不過，有些組織可能會有現有的 Office 365 磁碟使用量，以及可以有上述順序不同的進入點。 有四個一般設定：

- 沒有 Office 365 租用戶的多個同盟的內部部署組織。 在此情況下，從步驟 1 開始。
- 多個同盟的內部部署組織都已同步處理多個 Skype for Business 樹系到單一 Azure AD 租用戶。 此類組織的格式類似於圖，其已完成步驟 1-6，因此應開始執行步驟 7 中的假設組織。
- 同盟 1 混合組織或多個其他單純的內部部署組織，無的同步處理至 AAD。 此類組織會類似於假設組織**圖 E**，如下所示。
    - 此組織就類似於圖 B，已完成步驟 1-9、 除外：
        - 企業部署其非混合式商務用 Skype 會*不*尚未同步處理到 Azure AD。
        -  未尚未停用線上的 SIP 網域。 
    - 這些組織應該可以：
        - 完成移轉現有的混合式組織，然後輸入上述順序在步驟 10。  OR
        - 如果想要同步處理其他任何 Skype for Business 樹系至 AAD 之前完成移轉的混合式部署組織，則組織必須執行 [步驟的 7 （停用任何其他內部部署商務用 Skype 會的企業部署中的所有線上 SIP 網域至 AAD sync) 再啟用 [AAD Connect，並再繼續執行步驟 10 （解除委任原始的混合式部署中）。       
                **圖 E**<br>
                ![圖 E 圖表](../media/cloudconsolidationfige.png)
- 純粹 Skype 商務 Online 組織 （可能有或可能不使用 Teams） 的同盟與企業組織內部個別商務用 Skype。 一旦此組織會停用在內部部署組織的線上 SIP 網域，並讓 AAD Connect 用於企業組織內部部署商務用 Skype，看起來像假設組織**[圖 C](#figure-c)** 完成步驟 1-11 所示。

## <a name="limitations"></a>限制

- 最多只能有一個 Office 365 租用戶。 不支援多個 Office 365 租用戶案例的合併。
- 只有一個內部 Skype for Business 樹系可以是處於混合模式 （共用 SIP 位址空間），一次。 所有其他內部 Skype for Business 樹系必須保持純粹內部部署和應該與彼此和 Office 365 租用戶同盟。
- 之前要移轉至雲端，沒有非對稱經驗的使用者在此部署中，因為並非所有使用者在線上都會代表內部部署：
    - 體驗可以加總，如下所示：
        - 線上位於任何使用者好像使用者是混合式，將互動的混合式環境中的內部部署使用者。
        - 混合式部署中的內部部署使用者將會與線上好像它們是混合式表示其內部部署目錄中的使用者互動。 
        - 內部部署混合式部署中的使用者將互動 online 使用者不會出現在內部部署 AD 為同盟。
    - 在**[圖 D](#figure-d)** 上述使用者 E 是內部部署中 AcquiredCompany。<span>com。  使用者 E 與使用者 D （位於 online） 的互動方式使用標準的混合式的經驗，但使用者 E 會有同盟的經驗與使用者 A、 B 和 C，因為它們都不會出現在內部部署目錄中。 不過，使用者 A、 B 和 C 將互動使用者 E 好像使用者是在混合式架構。
    - 互動正在同盟與混合式的影響：
        - 目前狀態是不會自動訂閱的同盟使用者除非使用者會標示為 [連絡人。
        - 來電轉接同盟網域之間無法運作。
        - 來電轉接案例是較小。
        - 節流可能會套用到同盟流量。
- 指定此非對稱的經驗，正式支援在內部部署使用者與雲端使用者之間的跨單位部署案例中的通話功能不在內部部署目錄中限制為只對等。 
    - 來電轉接、 轉接、 通話佇列，這些使用者之間的等不受支援。
    - 這些不受支援的呼叫案例仍會出現已啟用，但在許多情況下他們將會失敗無法預期的方式。 
    - 在**[圖 D](#figure-d)** 上述使用者 E 是內部，而會做為對等支援與使用者 A、 B 或 C 的呼叫。 （與使用者 D 的通話不會有支援限制）。 不過，內部部署使用者 E 移至雲端後，此限制不會再套用。
- 如果您有多個部署的 Skype for Business Server 2019 環境中，這些部署的唯一 1 可以設定為使用組織的自動語音應答，因為該功能需要 Skype for Business Server 混合式組態。 
- 可以調整的一些先前的步驟順序。 必須符合的關鍵需求是，如果所有的這些都是，則為 true:
    - 多個內部 Skype for Business 樹系同步處理至單一 AAD 租用戶
    - 分割網域啟用其中一個內部部署樹系
    - 混合式組織中的至少一位使用者已移轉至雲端<br>   然後，您*必須*停用所有其他線上的 SIP 網域從任何其他內部部署商務用 Skype 商務樹系。 否則，online 使用者在其他組織中的混合式部署組織與內部部署使用者之間的同盟關係將會中斷一個方向。

## <a name="implications"></a>影響

- 因為有進階通話功能支援的限制，上面所述**組織應該將這些非對稱狀態視為暫時性一部分移轉，並不穩定的狀態為追求它們**。  
- 有多個內部部署商務用 Skype 商務部署的組織通常應該開頭可以完全移轉到雲端，部署，以便彙總可以繼續。 它也了解在某些情況下會有 holdouts 的對象還不可行，將移至 Teams 特定使用者群組。 當這項考量涉及多個 Skype for Business 樹系案例中的，開始移轉盡可能沒有這些限制的另一個樹系。
- 從內部部署移至雲端時，有委派關係及/或一般使用者參與案例應該視為一個單位一起移動的來電轉接。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>移至 TeamsOnly 模式的考量

當您將使用者從內部部署移至雲端混合式環境中時，您可以移動至任一 Skype 僅商務] 或 [TeamsOnly 模式。 *如果您打算將使用者移至 TeamsOnly 模式，請務必先閱讀這一節。*

- 當您將 TeamsOnly 模式指派給使用者時，所有聊天室和任何其他使用者的來電將會在該使用者的 microsoft Teams 用戶端都推送。 
- 如果使用者與 Skype 商務內部部署主要是使用 Skype 商務用戶端及不 Teams，請考慮設定 TeamsUpgradePolicy，以便路由傳送至內部部署使用者永遠堡而不是小組的商務用 Skype。 若要確保適當的路由傳送的聊天室和 TeamsOnly 的使用者還是會仍使用內部部署，商務用 Skype 使用者呼叫內部使用者必須有有效值 TeamsUpgradePolicy 以其中一個 SfB 模式中，而不是群島 (也就是預設值）。 
    - 若要這麼做，*您必須先將這些值的其中一個 TeamsUpgradePolicy 您租用戶的全域執行個體*：
        - SfBWithTeamsCollab （建議使用）
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 您可以使用此命令，以授與全租用戶原則：<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 附註： 您必須執行這項操作的全租用戶層級因為原則無法指派給個別使用者在線上目錄中，不需要 SIP 位址。 雖然您已停用內部純粹 deployment(s) 線上的 SIP 網域，這些網域中的使用者不會根據設計就線上目錄中有 SIP 位址。 因此，若要將原則套用至那些內部使用者的唯一方法是藉由指定租用戶層級。 相反地，在混合式架構部署使用者將 SIP 位址的目錄中有 online 讓他們可以明確指派原則如果它需要有不同的租用戶的全域原則的值。
- Microsoft Teams 用戶端 UX 不會尚未接受 TeamsUpgradePolicy SfB 模式。 例如，在這些模式中，當來電與交談初始 teams 是目前可行的雖然在未來，不會發生此情況。 這可能會造成使用者之間的混淆，因為回覆有時可能小組和有時商務用 Skype 中登陸狀況而定。 建議您分別停用通話並透過 TeamsMessagingPolicy 和 TeamsCallingPolicy 聊天室還是內部部署使用者。

## <a name="see-also"></a>另請參閱

[更新邊緣憑證](cloud-consolidation-edge-certificates.md)

[更新 AAD 連線至包含多個樹系](cloud-consolidation-aad-connect.md)

[停用混合式以完成移轉至雲端](cloud-consolidation-disabling-hybrid.md)
