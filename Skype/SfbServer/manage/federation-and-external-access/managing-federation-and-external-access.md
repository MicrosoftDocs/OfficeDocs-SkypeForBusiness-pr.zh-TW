---
title: Lync Server 2013：管理商務用 Skype Server 的同盟與外部存取
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以啟用並設定外部使用者存取權，以控制受支援的外部使用者是否可以與內部商務用 Skype 伺服器使用者共同作業。
ms.openlocfilehash: 366b65b53135388f4163154001f6400cc9fa2963
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818244"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理商務用 Skype Server 的同盟和外部存取

部署 Edge 伺服器或 Edge 池是支援外部使用者的第一個步驟。 如需有關部署邊緣伺服器的詳細資訊，請參閱[在商務用 Skype 伺服器中部署 Edge 伺服器](../../deploy/deploy-edge-server/deploy-edge-server.md)。

安裝並設定商務用 Skype Server 的內部部署之後，貴組織內的內部使用者就能與在 Active Directory 網域服務（AD DS）中擁有 SIP 帳戶的其他內部使用者共同作業。 共同作業可以包括傳送及接收立即訊息，以及更新目前狀態及參與會議（也稱為「會議」）。 您可以啟用並設定外部使用者存取權，以控制受支援的外部使用者是否可以與內部商務用 Skype 伺服器使用者共同作業。 外部使用者可以包含您部署的遠端使用者、同盟使用者（包括公用立即訊息（IM）服務提供者的支援使用者），以及會議中的匿名參與者。

如果您的部署包括安裝商務用 Skype Server Edge 伺服器或 Edge 池，可能的通訊類型的範圍會大大擴充，有許多外部使用者存取的選項，以及與其他 SIP 聯盟的成員進行通訊。網域和 SIP 聯盟提供者。 在設定 Edge 伺服器或 Edge 池之後，您可以啟用您想要提供的外部使用者存取類型，並設定控制外部存取的原則。 在商務用 Skype Server 中，您可以根據任務需求，使用商務用 Skype Server 控制台、[商務用 Skype Server 管理命令](../management-shell.md)介面（或兩者）來啟用及設定外部使用者存取與原則。 



> [!IMPORTANT]  
> 當您設計外部使用者存取的設定與原則時，您必須瞭解原則的優先順序，以及原則的套用方式。 在一個策略層級套用的商務用 Skype 伺服器原則設定，可以覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則（最具影響力）會覆寫網站原則，然後網站原則會覆寫全域原則（最小的影響）。 這表示原則設定越接近策略設定的物件，就會受到對物件的影響。


根據預設，不會將任何原則設定為支援外部使用者存取，包括遠端使用者存取、同盟使用者存取，即使您已為組織啟用外部使用者存取支援。 若要控制外部使用者存取的使用方式，您必須設定一或多個原則，以指定每個原則支援的外部使用者存取類型。 這包括下列外部存取原則：

  - **全域原則**   當您部署邊緣伺服器時，就會建立全域原則。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要支援全域層級的外部使用者存取，您可以將全域原則設定為支援一或多種類型的外部使用者存取選項。 全域原則會套用至貴組織中的所有使用者，但網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，就不會將它移除。 相反地，您可以將其重設為預設設定。

  - **網站原則**   您可以建立並設定一或多個網站原則，以限制外部使用者存取特定網站的支援。 網站原則中的設定優先於全域原則，但僅限該網站原則所涵蓋的特定網站。 例如，如果您在全域原則中啟用遠端使用者存取，您可以指定可停用特定網站之遠端使用者存取權的網站原則。 根據預設，網站原則會套用至該網站的所有使用者，但您可以將使用者原則指派給使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立及設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取權的支援。 使用者原則中的設定會覆寫全域和網站原則，但只適用于指派使用者原則的特定使用者。 例如，如果您在全域原則和網站原則中啟用遠端使用者存取，您可以指定可停用遠端使用者存取的使用者原則，然後將該使用者原則指派給特定的使用者。 如果您建立使用者原則，您必須先將其套用至一或多個使用者，才會生效。

若要判斷您需要建立或編輯哪些設定設定以及哪些原則，請參閱下列決策點：

**您想要讓您網域的內部和外部使用者能夠使用立即訊息、Web 會議和音訊/影片進行共同作業嗎？**

您可以在主題設定[控制遠端使用者可](external-access-policies/configure-policies-to-control-remote-user-access.md)傳遞的原則，以及[啟用或停用同盟與公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線等主題中的詳細資訊來設定設定。

**您想要允許匿名使用者出席並邀請您部署中的使用者所託管的會議嗎？**

設定主題[指派會議原則以支援匿名使用者](access-edge/assign-conferencing-policies-to-support-anonymous-users.md)及[建立會議原則](../conferencing/create-policies.md)中的詳細資訊。

**您想要允許使用者與 SIP 聯盟網域連絡人通訊嗎？**

您可以設定主題中的詳細資訊，例如[設定控制聯盟使用者存取的原則](external-access-policies/configure-policies-to-control-federated-user-access.md)、[啟用或停用同盟與公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[管理貴組織的 SIP 聯盟網域](sip-domains/manage-sip-federated-domains-for-your-organization.md)。


**如果您已啟用與 SIP 聯盟網域的通訊，您是否要啟用 SIP 同盟自動探索？**

在[啟用或停用同盟合作夥伴的探索](access-edge/enable-or-disable-discovery-of-federation-partners.md)主題中，設定設定的詳細資訊。

**如果您已啟用與 SIP 同盟網域的通訊，您是否要啟用將免責聲明傳送給同盟連絡人，通知他們您使用的是封存，而且該通訊可能已封存？**

如在[中啟用或停用將封存免責聲明傳送給聯盟合作夥伴，請](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)設定相關設定。

**您是否要允許使用者與 SIP 聯盟提供者通訊，以啟用與公用提供者的通訊？**

在主題中設定詳細資訊，以設定[控制公用使用者存取](external-access-policies/configure-policies-to-control-public-user-access.md)、[啟用或停用同盟與公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線的原則，以及[建立或編輯公用 SIP 聯盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**您是否要允許使用者與 SIP 同盟提供者通訊，這些提供者是執行 Microsoft Office 365 和商務用 Skype Online 的託管提供者？**

如需詳細資訊，請設定 [[啟用或停用同盟及公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線] 主題，以及[建立或編輯託管 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

**您的部署是在分割（也稱為混合式）網域中設定，有些使用者在內部部署中擁有其主伺服器，而其他使用者則是在線上環境中使用家用伺服器進行設定？**

您可以設定主題中的詳細資訊，例如[設定控制同盟使用者存取的原則](external-access-policies/configure-policies-to-control-federated-user-access.md)、[啟用或停用同盟與公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線，以及[建立或編輯託管 SIP 聯盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。


您可以設定外部使用者存取設定，包括任何您想要用來控制外部使用者存取權的原則，即使您的組織未啟用外部使用者存取權也一樣。 不過，您設定的原則和其他設定只有在您的組織啟用外部使用者存取後才會生效。 外部使用者在停用外部使用者存取權，或未設定外部使用者存取原則支援時，無法與貴組織的使用者進行通訊。

Edge 部署會驗證外部使用者的類型（匿名使用者除外，其由會議 ID 驗證，以及當您建立會議與邀請參與者時傳送給匿名參與者的密碼）。根據您設定 edge 支援的方式來存取。 若要控制通訊，您可以設定一或多個原則，並設定定義您的部署內部和外部的使用者之間相互通訊方式的設定。 [原則與設定] 包含外部使用者存取的預設全域原則，除了您可以建立並設定以啟用一或多種類型的外部使用者存取特定網站或使用者的網站和使用者原則之外。

