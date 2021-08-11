---
title: Teams 與商務用 Skype 的雲整合
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
description: 本文說明如何使用內部部署 (s) 商務用 Skype (或 Lync) ，以進行整合，以尋求將其 UC 工作負載移至 Teams 的組織。
ms.openlocfilehash: 268f9a7a35e53a514dda63c304c7a58e252004d3edf74d1342f4934ec4185aab
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54277458"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>Teams 和商務用 Skype 的雲端整合

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


許多大型企業擁有多個內部部署 AD 樹系，在某些情況下，客戶會有多個 Exchange 和/或商務用 Skype Server (或 Lync Server) 部署。 此外，即使是只有一個內部部署樹系的組織，透過企業併購的過程，也會發現自己處於類似的情況。 當這些客戶移至雲端時，他們想要將特定內部部署工作負載的多個實例合併到單一 Microsoft 365 組織中。 本文說明如何針對要將組織完全移至 Microsoft Teams 的商務用 Skype (或 Lync) 進行多個內部部署的整合， (所有使用者都只 Teams) 。

針對這類狀況的客戶，過去的指導方針是先合併內部部署的部署，然後再移至雲端。 雖然這仍是一個選項，本文也會說明可讓多個商務用 Skype 部署的組織同時將一個部署遷移到單一 Microsoft 365 組織，而不需要執行內部部署整合的解決方案。 請注意，Microsoft Teams 不支援具有單一 Microsoft 365 組織之混合模式中的多個商務用 Skype 或 Lync Server 樹系。 

> [!Important]
> 設定此指南之前，請務必複查並瞭解 [限制](#limitations)，因為它們可能會影響您的組織。

## <a name="overview-of-cloud-consolidation"></a>雲端整合概述

將內部部署中的所有使用者整合至單一 Microsoft 365 組織中的雲端，只要具備下列主要需求，便可滿足任何具有多個商務用 Skype 部署的組織：

- 最多隻能有一個 Microsoft 365 的組織參與。 不支援在具有多個組織之案例中進行合併。
- 任何時候，只有一個內部部署商務用 Skype 樹系可以處於混合模式 (共用 SIP 位址空間)。 其他所有內部部署商務用 Skype 樹系都必須仍是內部部署 (而且可能會互相形成同盟)。 請注意，如果您 [停用線上 SIP 網域](/powershell/module/skype/disable-csonlinesipdomain)，則其他內部部署組織 *可以* 在需要時同步到 Azure AD。

在多個樹系中部署商務用 Skype 的客戶，必須使用共用 SIP 位址空間功能，將單一混合商務用 Skype 樹系的所有使用者完全遷移到 Microsoft 365 組織中，然後再停用該內部部署的混合式，再繼續遷移下一個內部部署商務用 Skype 部署。 在移轉到雲端之前，內部部署使用者與任何不在相同使用者內部部署目錄中的使用者還是會保持同盟狀態。  

## <a name="canonical-example-of-cloud-consolidation"></a>雲端整合的規範範例

請考慮組織有兩個個別的同盟內部部署商務用 Skype，以在 Microsoft Teams 中將其合併為線上。


|原始狀態詳細資料 |期望的狀態詳細資料 |
|---------|---------|
|<ul><li>2獨立商務用 Skype 個別 AD 樹系中的內部部署部署<li>最多1個樹系與 Teams 混合在一起 <li> 組織 emc 相互同盟 <li>使用者未同步處理到這些樹系<li> 組織可能會有 Microsoft 365 組織，而且可能會將其目錄同步處理到 Azure AD</ul>|<ul> <li>1 Microsoft 365 組織<li>沒有其他的內部部署，因此不會有其他混合式部署<li>所有來自內部部署的使用者都已移至僅 Teams 模式 <li>商務用 Skype Server 無所不在都沒有內部部署的空間 <li>使用者仍有內部部署驗證</ul> |

![整合兩個不同的同盟內部部署](../media/cloudconsolidationfig1.png)  

從原始狀態到所需結束狀態的基本步驟如下。  請注意，有些組織可能會發現，在這些步驟中，有些組織可能會發現其起始點位於下列位置。 請參閱本文稍後的 [其他起始點](#other-starting-points)。 最後，在某些情況下，您可以根據需要調整順序。 稍後會說明[主要限制和限制](#limitations)。

1.  取得 Microsoft 365 組織（若有的話）。
2.  請確定已 Microsoft 365 網域驗證所有內部部署的相關 SIP 網域。
3.  挑選一個會與 Microsoft 365 混合的商務用 Skype 部署。 在此範例中，我們會使用 OriginalCompany。 <span>Com。
4.  為即將成為混合式 (OriginalCompany 的[樹系啟用 AAD 連線](configure-azure-ad-connect.md)。 <span>com) 。 
5.  將 [TeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy) 的承租人內部原則，設定為 SfBWithTeamsCollab 或其中一個其他 SfB 模式 (SfBOnly 或 SfBWithTeamsCollabAndMeetings) 。 這一點很重要，是要確保從僅限內部部署的使用者，移至 Teams 的使用者進行通話和聊天的路由。
6.  建議您在此點 (，但尚未必要，直到) 為[其他樹系啟用 AAD 連線](cloud-consolidation-aad-connect.md) (AcquiredCompany 為止。 <span>com) 。 假設這兩個樹系中皆已啟用 AAD 連線，則該組織看 **[起來像是](#figure-a)** 部分組織 emc 的常見起點。 
7.  針對其他內部部署所主控的任何 SIP 網域 (在此情況下，AcquiredCompany。 <span>com) ，請使用 Teams PowerShell 模組[停用 Microsoft 365 組織中的這些線上 SIP 網域](/powershell/module/skype/disable-csonlinesipdomain) `Disable-CsOnlineSipDomain` 。 
8.  為 OriginalCompany[設定商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)。 <span>com (仍已啟用線上 SIP 網域) 的一個部署。
9.  在混合部署中 (OriginalCompany。 <span>com) ，開始[將使用者從內部部署商務用 Skype 移至雲端](move-users-between-on-premises-and-cloud.md) (是否只 Teams 或不) ，這樣使用者才會 Teams。 現在，組織看起來如 **[圖 B](#figure-b)** 所示。圖 A 的主要變更如下：
    - 這兩個內部部署目錄中的使用者現在都在 AAD 中。
    - AcquiredCompany。 <span>com 是一種已停用的線上 SIP 網域。
    - 有些使用者已在線上移至 Teams。  (請參閱紫色使用者 A ) 
10. 將所有使用者移至雲端之後，請[停商務用 Skype 用 OriginalCompany 內部部署的混合式](cloud-consolidation-disabling-hybrid.md)。 <span>com 從 Microsoft 365：  
    - 停用 Microsoft 365 組織中的分割網域。
    - 停用與 OriginalCompany 中 Microsoft 365 通訊的功能。 <span>com 內部部署。
    - 更新 OriginalCompany 的 DNS 記錄。 <span>com 指向 Microsoft 365。
11. 若尚未完成，請啟用即將混合 (AcquiredCompany 之[下一個樹系的 AAD 連線](cloud-consolidation-aad-connect.md)。 <span>com) 。 此時，組織看起來如 **[圖 C](#figure-c)** 所示。這可能是部分組織的另一個常見起點。 
12. 在 Teams PowerShell 中，為即將混合式 AcquiredCompany 的[下一個內部部署啟用 SIP 網域](/powershell/module/skype/enable-csonlinesipdomain)。 <span>Com。 使用此功能的 `Enable-CsOnlineSipDomain` 方式，也就是2018年12月為止可用的新功能。
13. 如果您使用的是關閉的同盟，您必須 \* 在 **相同** Microsoft 365 中，將純線上租使用者 () 中的任何 SIP 網域新增為允許的網域。 請注意，您可能需要一段時間，變更才會生效，而且在初期執行這項動作時，我們建議您在移至步驟14之前做好這項工作。
14. 更新內部部署環境，以接受來自線上租使用者的任何 SIP 網域，使其符合。
    - 將[所有 edge 憑證中的 SAN 更新](cloud-consolidation-edge-certificates.md)為與 before 相同的值，再加上任何現有 online SIP 網域的值 (除了 microsoftonline.com) （在此例中為 OriginalCompany）。 <span>Com。
    - 請確定 OriginalCompany。 <span>com 是內部部署 AcquiredCompany 中的 [允許網域](/powershell/module/skype/new-csalloweddomain) 。 新增允許的網域。
15. 在內部部署 AcquiredCompany 之間[啟用商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)。 <span>com 和雲端。
16. 視需要，將 [使用者從內部部署遷移至雲端](move-users-between-on-premises-and-cloud.md) ，以成為 [TeamsOnly 使用者](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability)。 在此狀態下，組織看起來如 **[圖 D](#figure-d)** 所示。
17. 在遷移所有使用者之後，請 [停用內部部署環境的混合](cloud-consolidation-disabling-hybrid.md) 式， *使組織成為純雲端*！

下圖顯示在此程式期間，各個關鍵點的設定。

##### <a name="figure-a"></a>圖 A：

- 這兩個組織都透過 AAD 連線進行同步處理，因此 AAD 現在具有來自內部部署部署的所有使用者。
- 所有位於內部部署的使用者。  
- *尚未設定* 商務用 Skype 混合式。
- 如果兩個部署中的使用者都使用 Teams，他們將無法彼此同盟 (或任何組織) ，也不會與任何商務用 Skype 使用者進行交互操作。 在此階段中，Microsoft 建議您僅針對通道使用 Teams。<br><br>
    ![圖](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>圖 B：

- AcquiredCompany。 <span>com 是一種 [已停用](/powershell/module/skype/disable-csonlinesipdomain) 的線上 SIP 網域。 所有使用者都是內部部署。 如果他們使用 Teams 沒有同盟或互通性。 在此階段中，Microsoft 建議您僅針對通道使用 Teams。
- 已對其中一個內部部署組織啟用商務用 Skype 混合式。
- 混合組織中的某些使用者已移至雲端，而且只會 Teams (使用者 A，如紫色陰影) 所示。 這些使用者 Teams 只有使用者才能與其他任何商務用 Skype 使用者進行完全互通性及同盟支援。<br><br>
    ![圖 B 圖表](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>圖 C：

- OriginalCompany 中的所有使用者。 <span>com 現在只會在雲端中 Teams 模式。 
- 使用 OriginalCompany 商務用 Skype 混合式設定。 <span>已停用 com 部署。 內部部署已消失。
- 如果 AcquiredCompany。 <span>com 先前未同步處理至 AAD，若要從這裡繼續，必須立即同步處理。 不過，它尚未混合 (共用 SIP 位址空間) ，直到組織準備好移至混合式，純內部部署組織 (AcquiredCompany.com) 的線上 SIP 網域仍會保持停用狀態，以便線上 Teams 使用者可以與內部部署使用者通訊。<br><br>
    ![圖 C 圖表](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>圖 D：

- AcquiredCompany。 <span>com 現在已啟用為線上 SIP 網域。
- 內部部署已更新，可接受 OriginalCompany。 <span>Com。  (允許的網域和 edge 憑證都會) 更新。
- 在 AcquiredCompany 之間啟用共用 SIP 位址空間。 <span>com 和 Microsoft 365 組織。
- 混合式組織中的某些使用者可能已經移至雲端，例如， (紫色陰影) 所示的使用者 D。<br><br>
    ![圖 D 圖表](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>其他起始點

上述正常化範例中的步驟，會假設組織從兩個同盟內部部署部署開始，但沒有 Microsoft 365 目前狀態。 不過，有些組織可能會有現有的 Microsoft 365，但上述順序可能會有不同的進入點。 有四種一般設定：

- 無 Microsoft 365 組織的多個同盟內部部署組織。 在此情況下，從步驟1開始。
- 多個同盟內部部署組織，已將多個商務用 Skype 樹系同步處理至單一 Azure AD 租使用者。 這類組織類似于圖 A 中的假想組織，其已完成步驟1-6，應從步驟7開始。
- Federates 與一或多個其他純內部部署組織的混合式組織，其中任何一個同步處理到 AAD。 這類組織類似于 **圖 E** 中的假想組織，如下所示。
    - 此組織類似于圖 B，其已完成步驟1-9，但：
        - 其非混合式商務用 Skype *部署尚未同步* 處理至 Azure AD。
        -  線上 SIP 網域尚未停用。 
    - 這些組織應執行下列其中一項操作：
        - 完成現有的混合式組織的遷移，並在步驟10輸入上述順序。  或
        - 若要在完成混合式組織的遷移之前，將其他任何商務用 Skype 樹系同步處理至 aad，組織必須執行步驟 7 (停用任何其他內部部署商務用 Skype 部署中的所有線上 SIP 網域，以同步處理至 AAD) ，然後再繼續步驟10連線解除委任原始混合部署 (。       
                **圖 E**<br>
                ![圖 E 圖表](../media/cloudconsolidationfige.png)
- 純 Teams 只有與個別內部部署商務用 Skype 組織 federates 的組織。 一旦此組織停用內部部署組織的線上 SIP 網域，並為內部部署商務用 Skype 組織啟用 AAD 連線，它就會類似于已完成步驟1-11 的 **[圖 C](#figure-c)** 所示的假想組織。

## <a name="limitations"></a>限制

- 最多隻能有一個 Microsoft 365 的組織參與。 不支援在具有多個組織之案例中進行合併。
- 一次只能有一個內部部署商務用 Skype 樹系 (共用 SIP 位址空間) 的混合模式。 其他所有的內部部署商務用 Skype 樹系都必須完全保持內部部署，且應彼此同盟與 Microsoft 365 組織。
- 在遷移至雲端之前，不會在此部署中使用使用者的非對稱體驗，因為並非線上中的所有使用者都是以內部部署表示：
    - 這種體驗的求和方式如下：
        - 任何位於線上的使用者都會與混合式環境中的內部部署使用者互動，如同使用者是混合式。
        - 混合式部署中的內部部署使用者會與線上使用者互動，其內部部署目錄中的使用者會如同混合式。 
        - 混合式部署中的內部部署使用者將與在內部部署 AD 中未以同盟方式表示的線上使用者互動。
    - 在上 **[圖](#figure-d)** 中，使用者 E 是內部部署的 AcquiredCompany。 <span>Com。  使用者 E 會使用標準混合式體驗與使用者 D (穴) 進行互動，但使用者 E 會與使用者 A、B 和 C 的同盟經驗進行互動，因為它們不會在內部部署目錄中呈現。 不過，使用者 A、B 和 C 會與使用者 E 互動，就如同該使用者是在混合式。
    - 混合式與同盟的影響：
        - 除非使用者標示為連絡人，否則不會自動為同盟使用者訂閱顯示狀態。
        - 「來電轉接」無法在同盟網域之間運作。
        - 來電轉接案例更為有限。
        - 節流可以套用到同盟流量。
- 已知此非對稱體驗，在內部部署使用者與不在內部部署目錄中的雲端使用者之間的跨部署案例中，對呼叫功能的官方支援，只限于對等。 
    - 不支援這些使用者之間的來電轉接、轉接、通話佇列等。
    - 這些不支援的呼叫案例仍會出現啟用，但是在許多情況下，它們會以無法預測的方式失敗。 
    - 在上 **[圖](#figure-d)** 中，使用者 E 是內部部署的，而且使用者 A、B 或 C 的呼叫只會支援對等。  (使用者 D 的呼叫不會有支援限制。 ) 不過，在內部部署使用者 E 移至雲端之後，就不再套用此限制。
- 如果您的環境中有一個以上的商務用 Skype Server 2019 部署，則只有其中一個部署可以設定為使用組織的自動語音應答，因為該功能需要商務用 Skype Server 混合式設定。 
- 您可以調整某些先前步驟的順序。 必須滿足的主要需求是，如果全部都為 true：
    - 一個以上的內部部署商務用 Skype 樹系同步處理至 Azure AD 中的單一 Microsoft 365 租使用者。
    - 使用一個內部部署樹系啟用分割網域
    - 混合式組織中至少有一位使用者已遷移至雲端<br>   然後，您 *必須* 從任何其他內部部署商務用 Skype 樹系停用所有其他線上 SIP 網域。 否則，混合式組織中的線上使用者與其他組織中的內部部署使用者之間的同盟將會以單一方向中斷。

## <a name="implications"></a>影響

- 由於上述高級呼叫功能的支援限制，如上述所述， **組織應該將這些非對稱狀態視為遷移的一部分，而不是將其視為穩定狀態**。  
- 具有多個內部部署商務用 Skype 部署的組織一般會從可以完全遷移至雲端的部署開始，以繼續整合。 在某些情況下，在某些情況下，可能會有 holdouts 某些使用者群組尚未可行，無法移至 Teams。 當此考慮涉及多個商務用 Skype 樹系的案例時，請從其他沒有這些限制的樹系開始進行遷移（若有的話）。
- 從內部部署移至雲端時，具有委派關聯和/或的使用者通常會包含在來電轉接案例中，以整體方式移動。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>移至 TeamsOnly 模式的考慮

當您從內部部署將使用者移至混合式環境中的雲端時，這些使用者只會變成 Teams 使用者。

- 當您為使用者指派 TeamsOnly 模式時，任何其他使用者的所有交談及通話都會在該使用者的 Teams 用戶端中。 
- 如果商務用 Skype 內部部署的使用者主要使用商務用 Skype 用戶端，而不是 Teams，請考慮設定 TeamsUpgradePolicy，以便路由傳送至那些內部部署使用者永遠都在商務用 Skype 而非 Teams。 為了確保在 TeamsOnly 的使用者和仍在內部使用商務用 Skype 的使用者間正確路由交談及通話，內部部署使用者必須具有 SfB 模式之一的有效值，而不是預設) 的孤島 (。 
    - 若要這麼做， *您必須先將租使用者的全域實例設定為下列其中一個值 TeamsUpgradePolicy*：
        - SfBWithTeamsCollab (建議) 
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 您可以使用下列命令授與租使用者的原則：<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 附注：您必須在租使用者層級執行此作業，因為原則無法指派給在線上目錄中沒有 SIP 位址的個別使用者。 當您已停用純內部部署 () 的線上 SIP 網域時，這些網域中的使用者將不會以設計方式在線上目錄中擁有 SIP 位址。 因此，將原則套用至內部部署使用者的唯一方法是在租使用者層級指派。 相反地，在混合部署中，使用者會在線上目錄中擁有 SIP 位址，以便在需要與租使用者通用原則不同的值的情況下，明確指派原則。

## <a name="see-also"></a>另請參閱

[更新 Edge 憑證](cloud-consolidation-edge-certificates.md)

[更新 AAD Connect 以包含多個樹系](cloud-consolidation-aad-connect.md)

[停用混合式以完成移轉至雲端](cloud-consolidation-disabling-hybrid.md)
