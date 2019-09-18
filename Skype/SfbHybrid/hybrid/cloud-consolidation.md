---
title: 團隊與商務用 Skype 的雲端整合
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文說明如何使用商務用 Skype （或 Lync）的內部部署（或 Lync）部署來取得該整合，以將其 UC 工作負載移至團隊和/或商務用 Skype Online。
ms.openlocfilehash: 33cbc823fd7aeece1591810d63d2ebf4a348237a
ms.sourcegitcommit: 6b73b89f29a0eabbd9cdedf995d5325291594bac
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2019
ms.locfileid: "37018842"
---
# <a name="cloud-consolidation-for-teams-and-skype-for-business"></a>團隊與商務用 Skype 的雲端整合

許多大型企業都有一個以上的內部部署 AD 目錄林，在某些情況下，客戶有一個以上的 Exchange 和/或商務用 Skype 伺服器（或 Lync Server）部署。 此外，即使只有一個內部部署目錄林的組織，也能透過商業兼併或收購，在類似情況中找到自己。 當這些客戶移至雲端時，他們想要將特定內部部署工作負載的多個實例合併到雲端，成為單一的 Office 365 租使用者。 本文說明如何針對有多個內部部署的商務用 Skype （或 Lync），將其 UC 工作負載移至 Microsoft 雲端（例如，Microsoft 團隊和/或商務用 Skype Online），為組織實現這項整合。

在過去，在這種情況下，客戶必須先整合部署內部部署，然後再移至雲端。 雖然這仍是一個選項，本文將說明一個以新功能為基礎的解決方案，此方案可讓具有多個商務用 Skype 部署的組織一次將一個部署遷移到單一的 Office 365 租使用者，而不需要進行內部部署方案. 請注意，即使使用這項新功能，商務用 Skype Online 和 Microsoft 團隊不支援使用單一 Office 365 租使用者的混合模式的多個商務用 Skype/Lync 目錄林。 

> [!Important]
> 使用本指南進行設定之前，請務必審查並瞭解[限制](#limitations)，因為它們可能會影響您的組織。

## <a name="overview-of-cloud-consolidation"></a>雲端整合概述

只要符合下列主要需求，就可以將內部部署中的所有使用者合併到單一 Office 365 租使用者，以取得任何組織使用多個商務用 Skype 部署的方案：

- 最多隻能有一個 Office 365 租使用者。 不支援在多個 Office 365 租使用者的案例中整合。
- 在任何指定時間，只有一個內部部署的商務用 Skype 目錄林可以混合模式（共用的 SIP 位址空間）。 所有其他內部部署的商務用 Skype 目錄林都必須在內部部署（且可互相聯盟）。 請注意，如果您想[要使用新功能來停](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain?view=skype-ps)用從2018年12月起提供的線上 SIP 網域，則這些其他內部部署組織*可以*同步處理到 AAD。

在多個樹林中部署商務用 Skype 的客戶，必須將單一混合式商務用 Skype 目錄林的所有使用者，分別完整地遷移到 Office 365 租使用者，並使用共用的 SIP 位址空間功能，然後停用混合式內部部署，在繼續之前，您必須先開始進行商務用 Skype 部署。 在遷移到雲端之前，內部部署使用者會與任何不在同一個使用者的內部部署目錄中的使用者保持聯合狀態。  

## <a name="canonical-example-of-cloud-consolidation"></a>雲端整合的規範範例

假設有一個組織有兩個獨立的商務用 Skype 內部部署，該企業想要在 Microsoft 團隊或商務用 Skype Online 中將其合併為線上。


|原始狀態詳細資料 |所需的狀態詳細資料 |
|---------|---------|
|<ul><li>2個獨立 AD 目錄林中的商務用 Skype 內部部署部署<li>最多1個目錄林與商務用 Skype Online 的混合式 <li> 組織相互同盟 <li>使用者不會同步處理到這些目錄林<li> 組織可能擁有 Office 365 租使用者，並且可能會將其目錄同步處理到 Azure AD</ul>|<ul> <li>1個 Office 365 租使用者<li>沒有其他內部部署，因此沒有任何混合式部署<li>內部部署中的所有使用者都是在商務用 Skype Online 中託管，而且也可以選擇僅供團隊使用者使用 <li>在任何地方都沒有任何內部部署的商務用 Skype <li>使用者仍然有內部部署驗證</ul> |

![合併兩個個別的聯合內部部署部署](../media/cloudconsolidationfig1.png)  

從原始狀態到所需結束狀態的基本步驟如下所示。  請注意，某些組織可能會發現它們的起點是位於這些步驟中間的某個位置。 請參閱本文稍後的[其他起始點](#other-starting-points)。 最後，在某些情況下，可以根據需求調整訂單。 稍後會說明[主要限制與限制](#limitations)。

1.  如果 Office 365 租使用者尚不存在的話，請取得該租使用者。
2.  請確定所有在內部部署部署中的相關 SIP 網域都已驗證為 Office 365 網域。
3.  挑選一個將與 Office 365 混合的商務用 Skype 部署。 在這個範例中，我們將使用 OriginalCompany。<span>com。
4.  針對將最先變成混合式（OriginalCompany）的[林，啟用 AAD Connect](configure-azure-ad-connect.md) 。<span>com）。 
5.  如果您要將團隊引入您的組織，請將[TeamsUpgradePolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-csteamsupgradepolicy)的租使用者原則設定為 SfBWithTeamsCollab 或其他其中一個 SfB 模式（SfBOnly 或 SfBWithTeamsCollabAndMeetings）。 這對於保證只向已在內部部署的使用者移動至團隊的使用者，這是一項重要的功能。
6.  我們建議您在此情況下（但在步驟11之前還不需要），為其他林（AcquiredCompany）[啟用 AAD Connect](cloud-consolidation-aad-connect.md) 。<span>com）。 假設在兩個目錄林中都啟用 AAD Connect，組織看起來**[就像是](#figure-a)** 一些組織的常見起點。 
7.  針對由其他內部部署部署（在此案例中為 AcquiredCompany）託管的任何 SIP<span>網域。com），請在 PowerShell 中使用`Disable-CsOnlineSipDomain` [商務用 Skype Online 停用這些 SIP 網域](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)。 （這是從2018年12月起的新功能。）
8.  針對 OriginalCompany[設定商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)式。<span>com （一種仍啟用線上 SIP 網域的部署）。
9.  在混合式部署（OriginalCompany）<span>中。com）中，[從商務用 skype 開始將使用者移至雲端](move-users-between-on-premises-and-cloud.md)（無論是否僅限團隊），讓該帳戶駐留在商務用 skype Online 中。 現在，組織看起來像是**[圖 B](#figure-b)**。圖 A 的主要變更如下：
    - 來自內部部署目錄的使用者現在都在 AAD 中。
    - AcquiredCompany.<span>com 是已停用的線上 SIP 網域。
    - 有些使用者已線上移至商務用 Skype Online 或團隊。 （請參閱紫色使用者 A。）
10. 將所有使用者移至雲端之後，請[停用商務用 Skype 內部部署](cloud-consolidation-disabling-hybrid.md)OriginalCompany 的混合式。<span>從 Office 365 的 com：  
    - 停用 Office 365 租使用者中的分割網域。
    - 停用 OriginalCompany 中與 Office 365 通訊的功能。<span>com 內部部署。
    - 更新 OriginalCompany 的 DNS 記錄。<span>[com]，指向 [Office 365]。
11. 如果還沒有完成，請[針對下一個](cloud-consolidation-aad-connect.md)將成為混合式（AcquiredCompany）的林啟用<span> AAD 連線。com）。 此時，組織看起來像**[圖 C](#figure-c)**。這可能是一些組織的另一個常見起點。 
12. 在 PowerShell 中，針對下一個將會成為混合式 AcquiredCompany 的[內部部署部署啟用 SIP 網域](https://docs.microsoft.com/en-us/powershell/module/skype/enable-csonlinesipdomain?view=skype-ps)。<span>com。 此完成是使用`Enable-CsOnlineSipDomain`，這是從2018年12月起提供的新功能。
13. 如果您使用的是已關閉的同盟，您必須在**相同**的 Office 365 中將純粹線上租使用者的任何 SIP 網域（不包括 *. microsoftonline.com）新增為允許的網域。 請注意，變更可能需要一些時間才會生效，而且儘早進行這項工作，因此我們建議您在移至步驟14前進行這項工作。
14. 更新內部部署環境，以接受來自線上租使用者的任何 SIP 網域，使其相符。
    - 將[所有邊緣憑證中的 SAN 更新](cloud-consolidation-edge-certificates.md)為與之前相同的值，加上任何現有線上 SIP 網域（除了 * microsoftonline.com）的值（在此例中為 OriginalCompany）。<span>com。
    - 請確定 OriginalCompany。<span>在內部部署中，Com 是 AcquiredCompany 的[允許網域](https://docs.microsoft.com/en-us/powershell/module/skype/new-csalloweddomain)。 新增 [允許的網域]。
15. 在內部部署 AcquiredCompany 之間[啟用商務用 Skype 混合](configure-federation-with-skype-for-business-online.md)式。<span>com 和雲端。
16. 視需要，[將使用者從內部部署遷移到雲端](move-users-between-on-premises-and-cloud.md)。 您可以直接將使用者遷移至[TeamsOnly](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability)模式，或者您可以先將使用者遷移到商務用 Skype Online。 在此狀態中，組織看起來像**[圖 D](#figure-d)**。
17. 遷移完所有使用者之後，請[停用與內部部署環境混合使用的方式](cloud-consolidation-disabling-hybrid.md)，*讓組織成為純粹的雲端*！

下圖顯示的是此程式期間各個重點的配置。

##### <a name="figure-a"></a>圖 A：

- 兩個組織都透過 AAD Connect 進行同步處理，因此 AAD 現在擁有來自內部部署部署的所有使用者。
- 所有使用者都駐留在內部部署。  
- *尚未設定*商務用 Skype 混合式。
- 如果任一部署的使用者都使用團隊，他們將無法彼此聯盟（或任何組織），也無法與任何商務用 Skype 使用者進行互通性。 在此階段中，Microsoft 建議僅將團隊用於頻道。<br><br>
    ![圖](../media/cloudconsolidationfiga.png)

##### <a name="figure-b"></a>圖 B：

- AcquiredCompany.<span>com 是[已停用](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)的線上 SIP 網域。 所有使用者都是內部部署。 如果他們使用的團隊沒有聯盟或互通性。 在此階段中，Microsoft 建議僅將團隊用於頻道。
- 已針對其中一個內部部署組織啟用商務用 Skype 混合式。
- 混合式組織中的部分使用者已經移至雲端（使用者 A 由紫色陰影所示）。 這些使用者可以是商務用 Skype Online 使用者，或只有擁有完整互通性與同盟支援的使用者。<br><br>
    ![圖 B 圖表](../media/cloudconsolidationfigb.png)

##### <a name="figure-c"></a>圖 C：

- 從 OriginalCompany 的所有使用者。<span>com 現已在雲端（駐留在商務用 Skype Online 中）。 建議它們也只是團隊。
- 商務用 Skype 混合式設定與 OriginalCompany。<span>com 部署已停用。 內部部署部署已消失。
- 如果 AcquiredCompany。<span>com 先前沒有同步處理到 AAD，若要從這裡繼續，您必須立即同步處理。 但尚未混合（共用的 SIP 位址空間），直到組織準備好要移至混合式之後，純粹是內部部署組織（AcquiredCompany.com）的線上 SIP 網域仍會保持停用狀態，讓線上團隊使用者可以與之通訊內部部署使用者。<br><br>
    ![圖 C 圖表](../media/cloudconsolidationfigc.png)

##### <a name="figure-d"></a>圖 D：

- AcquiredCompany.<span>com 現在已啟用為線上 SIP 網域。
- 內部部署已更新，以接受 OriginalCompany。<span>com。 （[允許的網域] 和 [邊緣證書] 都會更新）。
- 在 AcquiredCompany 之間啟用共用的 SIP 位址空間。<span>Com 與 Office 365 租使用者。
- 混合式組織中的部分使用者可能已經移至雲端，例如下方的使用者 D （以紫色陰影表示）。<br><br>
    ![圖 D 圖表](../media/cloudconsolidationfigd.png)

## <a name="other-starting-points"></a>其他起始點

上述規範範例中的步驟，假設組織是從兩個沒有 Office 365 目前狀態的同盟內部部署部署開始進行。 不過，有些組織可能已有 Office 365 的需求量，且上述順序中可能會有不同的進入點。 共有四種典型配置：

- 多個不含 Office 365 租使用者的共同聯盟內部部署組織。 在這種情況下，從步驟1開始。
- 已將多個商務用 Skype 目錄林同步處理到單一 Azure AD 租使用者的多個聯合內部部署組織。 這類組織就像是圖 A 中的假想組織，該組織已完成步驟1-6，且應從步驟7開始。
- 與一或多個其他純粹內部部署組織 federates 的混合式組織，沒有任何同步處理到 AAD。 這類組織與**圖 E**中的假想組織類似，如下所示。
    - 此組織類似于圖 B，也就是已完成步驟1-9，但不包括：
        - 其非混合式商務用 Skype*部署尚未同步*處理到 Azure AD。
        -  線上 SIP 網域尚未停用。 
    - 這些組織必須：
        - 完成現有混合式組織的遷移，然後在步驟10中輸入上述順序。  或
        - 如果您想要在完成混合式組織前將任何其他的商務用 Skype 目錄林同步處理到 AAD，組織必須執行步驟7（在任何其他內部部署商務用 Skype 部署中停用所有線上 SIP 網域，將同步處理到 AAD），然後啟用 AAD Connect，然後只繼續執行步驟10（解除原始混合式部署）。       
                **圖 E**<br>
                ![圖 E 圖表](../media/cloudconsolidationfige.png)
- 使用個別的內部部署商務用 Skype 組織 federates 的純粹商務用 Skype Online 組織（可能會有，也可能不會使用團隊）。 一旦此組織停用內部部署組織的線上 SIP 網域，並為內部部署商務用 Skype 組織啟用 AAD 連線，就像是**[圖 C](#figure-c)** 所示的假想組織，已完成步驟1-11。

## <a name="limitations"></a>有限

- 最多隻能有一個 Office 365 租使用者。 不支援在多個 Office 365 租使用者的案例中整合。
- 只有一個內部部署商務用 Skype 目錄林可以一次使用混合式模式（共用的 SIP 位址空間）。 所有其他內部部署的商務用 Skype 目錄林都必須完全保持在內部部署狀態，且應該彼此同盟與 Office 365 租使用者。
- 在遷移到雲端之前，此部署中的使用者無法使用非對稱體驗，因為並非線上中的所有使用者都以內部部署的方式呈現：
    - 您可以將體驗總結如下：
        - 任何駐留在線上的使用者，都會與混合式環境中的內部部署使用者互動，就像該使用者是混合式式。
        - 混合式部署中的內部部署使用者將會與在其內部部署目錄中呈現的線上使用者互動，就好像它們是混合式。 
        - 混合式部署中的內部部署使用者將與不在內部部署廣告中的線上使用者進行互動。
    - 在上述**[圖 D](#figure-d)** 中，使用者 E 在 AcquiredCompany 中是內部部署的。<span>com。  使用者 E 會使用標準混合式體驗與使用者 D （託管線上）互動，但使用者 E 將具備與使用者 A、B 和 C 的同盟體驗，因為它們不是在內部部署目錄中表示。 不過，使用者 A、B 和 C 會與使用者 E 互動，就像使用者是混合式。
    - 混合式與同盟的影響：
        - 除非使用者標示為連絡人，否則不會針對聯盟使用者自動訂閱目前狀態。
        - [來電轉接] 無法在聯盟網域之間運作。
        - 來電轉接案例的限制較多。
        - 節流可能會套用到聯盟流量。
- 已知此非對稱體驗，在內部部署使用者與不在內部部署目錄中的雲端使用者之間，在跨內部部署案例中呼叫功能的正式支援僅限對等對等。 
    - 不支援在這些使用者之間進行來電轉接、轉接、通話佇列等。
    - 這些不支援的呼叫案例仍會顯示為啟用狀態，但在許多情況下，它們會以無法預知的方式失敗。 
    - 在上述**[圖 D](#figure-d)** 中，使用者 E 是內部部署的，而且與使用者 A、B 或 C 的呼叫只會在對等的情況下受到支援。 （使用者 D 的通話不會提供支援限制。） 不過，在內部部署使用者 E 移到雲端之後，此限制將不再適用。
- 如果您的環境中有一個以上的商務用 Skype Server 2019 部署，則只有其中一個部署可以設定為使用組織的自動語音應答，因為該功能需要商務用 Skype Server 混合式配置。 
- 您可以調整前面幾個步驟的順序。 必須符合的主要需求就是如果所有這些都成立：
    - 多個內部部署商務用 Skype 目錄林同步處理到單一 AAD 租使用者
    - 使用一個內部部署目錄林啟用分割網域
    - 混合式組織中至少有一個使用者已遷移到雲端<br>   接著，您*必須*從任何其他內部部署商務用 Skype 目錄林停用所有其他的線上 SIP 網域。 否則，混合式組織中的線上使用者與其他組織中的內部部署使用者之間的同盟會在一個方向中斷。

## <a name="implications"></a>含意

- 由於上述高級呼叫功能支援的限制（如上所述），**組織應該將這些非對稱狀態看作是遷移的一部分，而不是將它們視為穩定狀態**。  
- 具有多個內部部署商務用 Skype 部署的組織，一般都是從可完全遷移到雲端的部署開始，因此可繼續進行整合。 在某些情況下，在某些情況下，可能會有一些使用者群組無法移至團隊的 holdouts。 在涉及多個商務用 Skype 目錄林的案例中，若有可能的話，請開始與另一個沒有這些限制的林進行遷移。
- 從內部部署移至雲端時，具有委派關聯及/或的使用者通常都要在來電轉接案例中，以一個單元來移動。

## <a name="considerations-for-moving-to-teamsonly-mode"></a>移至 TeamsOnly 模式的考慮

當您將使用者從內部部署移至混合式環境中的雲端時，您可以將他們移至 [僅供商務用 Skype] 或 [TeamsOnly 模式]。 *如果您打算將使用者移至 TeamsOnly 模式，請務必先閱讀本節。*

- 當您將 TeamsOnly 模式指派給使用者時，任何其他使用者的聊天和呼叫都會集中在該使用者的團隊用戶端中。 
- 如果使用商務用 Skype 內部部署的使用者主要是使用商務用 Skype 用戶端，而不是團隊，請考慮設定 TeamsUpgradePolicy，讓路由到那些內部部署的使用者，而不是團隊。 為了確保在 TeamsOnly 的使用者以及仍在內部部署中使用商務用 Skype 的使用者之間正確地路由聊天和通話，內部部署使用者必須具備有效的 TeamsUpgradePolicy 值，而不是孤島（這是預設值）。 
    - 若要這樣做，*您必須先將租使用者的 TeamsUpgradePolicy 全域實例設定為下列其中一個值*：
        - SfBWithTeamsCollab （建議使用）
        - SfBWithTeamsCollabAndMeetings
        - SfBOnly
    - 您可以使用此命令來授與租使用者的原則：<br>`Grant-CsTeamsUpgradePolicy -PolicyName SfBWithTeamsCollab -Global`
    - 注意：您必須在租使用者層級執行此動作，因為原則無法指派給在線上目錄中沒有 SIP 位址的個別使用者。 在您針對純粹內部部署的部署停用線上 SIP 網域時，這些網域中的使用者在線上目錄中將不會有設計的 SIP 位址。 因此，將原則套用到內部部署使用者的唯一方式是指派給租使用者層級。 相反地，混合式部署使用者會在線上目錄中擁有 SIP 位址，以便在您想要的原則必須與租使用者全域原則不同的值時，才能明確指派原則。
- 團隊用戶端 UX 還不會服從 TeamsUpgradePolicy 的 SfB 模式。 例如，在這些模式中，目前可以在小組中撥打電話與聊天，但在未來不是如此。 這可能會造成使用者之間的混淆，因為回復有時可能會以小組和商務用 Skype （視情況而定）。 建議您針對仍在內部部署的使用者，分別停用 TeamsMessagingPolicy 和 TeamsCallingPolicy 的通話和聊天。

## <a name="see-also"></a>另請參閱

[更新邊緣憑證](cloud-consolidation-edge-certificates.md)

[更新 AAD Connect 以包含一個以上的林](cloud-consolidation-aad-connect.md)

[停用混合式完成到雲端的遷移](cloud-consolidation-disabling-hybrid.md)
