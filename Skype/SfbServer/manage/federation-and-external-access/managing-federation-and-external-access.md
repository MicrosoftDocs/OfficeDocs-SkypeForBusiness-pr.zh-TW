---
title: Lync Server 2013：管理對商務用 Skype Server 的同盟與外部存取
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 您可以啟用和設定外部使用者存取，以控制是否支援的外部使用者能夠與內部商務用 Skype Server 使用者共同作業。
ms.openlocfilehash: 2521d3f4d4134c4edb89904e5a7db4e4026b79e6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743549"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理商務用 Skype Server 的同盟與外部存取

支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。 如需部署 edge server 的詳細資訊，請參閱[Deploy edge Server in 商務用 Skype Server](../../deploy/deploy-edge-server/deploy-edge-server.md)。

在安裝和設定商務用 Skype Server 的內部部署之後，您組織中的內部使用者可以與在您的 Active Directory 網域服務中具有 SIP 帳戶的其他內部使用者進行共同作業。 (AD DS) 。 共同作業可包含傳送和接收立即訊息，以及會議中目前狀態與參加情況的更新。 您可以啟用和設定外部使用者存取，以控制是否支援的外部使用者能夠與內部商務用 Skype Server 使用者共同作業。 外部使用者可以包含您部署的遠端使用者，同盟使用者 (包括支援的公用立即訊息使用者 (IM) 服務提供者) 及會議中的匿名參與者。

如果您的部署包含安裝的商務用 Skype Server Edge Server 或 Edge 集區，則可能的通訊類型的範圍會極大地擴充，具有許多選項可供外部使用者存取、與其他 sip 同盟網域和 sip 同盟提供者的成員進行通訊。 在設定 Edge Server 或 Edge 集區之後，請啟用您要提供的外部使用者存取類型，並設定原則以控制外部存取。 在商務用 Skype Server 中，您可以根據任務需求，使用商務用 Skype Server 控制台、[商務用 Skype Server 管理命令](../management-shell.md)介面或兩者來啟用及設定外部使用者存取和原則。 



> [!IMPORTANT]  
> 當您設計外部使用者存取的組態和原則時，必須知道原則的優先順序以及原則的套用方式。 商務用 Skype Server 于一個原則層級套用的原則設定，會覆寫在其他原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。


根據預設，沒有原則是設定為支援外部使用者存取 (包括遠端使用者存取、同盟網域使用者存取)，即使您已為組織啟用外部使用者存取也一樣。若要控制外部使用者存取的使用，您必須設定一個或多個原則，並在每個原則指定支援的外部使用者存取類型。這包括下列外部存取原則：

  - **全域原則**   全域原則是在您部署 Edge Server 時建立。根據預設，全域原則中不會啟用任何外部使用者存取選項。若要在全域層級支援外部使用者存取，您必須設定全域原則為支援一或多個外部使用者存取類型選項。全域原則會套用至組織內所有使用者，但網站原則和使用者原則會覆寫全域原則。如果刪除全域原則，並不代表將其移除，而是將其重設回預設設定。

  - **網站原則**   您可以建立並設定一或多個網站原則，以對特定網站限制外部使用者存取支援。網站原則中的設定會覆寫全域原則，但僅限於該網站原則所涵蓋的特定網站。例如，如果您在全域原則中啟用了遠端使用者存取，您可以指定網站原則以對特定網站停用遠端使用者存取。根據預設，網站原則會套用至該網站的所有使用者，但您可以指派使用者原則給個別使用者，以覆寫網站原則設定。

  - **使用者原則**   您可以建立並設定個或多個使用者原則，以對特定使用者限制遠端使用者存取支援。使用者原則中的設定會覆寫全域與網站原則，但僅限於該使用者原則指派的特定使用者。例如，如果您在全域原則和網站原則中啟用了遠端使用者存取，您可以指定使用者原則以停用遠端使用者存取，然後將該使用者原則指派給特定使用者。如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。

若要決定需要建立或編輯哪些組態設定及原則，請參閱下列決策要點：

**您是否要允許您網域的內部及外部使用者能夠使用立即訊息、Web 會議及音訊/視訊來共同作業？**

設定各主題所述的設定，以 [控制遠端使用者的可](external-access-policies/configure-policies-to-control-remote-user-access.md)接入的原則，以及 [啟用或停用同盟與公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線。

**您是否要允許匿名使用者加入您部署中使用者所主控的會議，以及收到該會議的邀請？**

設定如需詳細資訊，請將設定 [指派會議原則以支援匿名使用者](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) 並 [建立會議原則](../conferencing/create-policies.md)。

**您是否要允許使用者與 SIP 同盟網域連絡人進行通訊？**

設定各主題的詳細資訊。設定 [控制同盟使用者存取的原則](external-access-policies/configure-policies-to-control-federated-user-access.md)、 [啟用或停用同盟與公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線，以及 [管理組織的 SIP 同盟網域](sip-domains/manage-sip-federated-domains-for-your-organization.md)。


**若您已啟用與 SIP 同盟網域的通訊，您是否要啟用 SIP 同盟自動探索？**

如需 [啟用或停用同盟](access-edge/enable-or-disable-discovery-of-federation-partners.md)協力廠商的探索主題所述，設定設定。

**若您已啟用與 SIP 同盟網域的通訊，您是否還要啟用傳送免責聲明給同盟連絡人，以通知他們您使用了封裝功能，且可能會封裝通訊內容？**

在主題中 [啟用或停用傳送封存免責聲明至同盟合作夥伴](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)的詳細資訊，設定這些設定。

**您是否要允許使用者與啟用公用提供者通訊的 SIP 同盟提供者通訊？**

設定各主題的詳細資訊設定 [原則以控制公用使用者存取](external-access-policies/configure-policies-to-control-public-user-access.md)、 [啟用或停用同盟和公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線，以及 [建立或編輯公用 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)


**您是否要允許使用者與執行 Microsoft 365 或 Office 365 並商務用 Skype 線上之主機的 SIP 同盟提供者通訊？**

設定各主題的詳細資訊。 [啟用或停用同盟和公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 連線，並 [建立或編輯主控的 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。

**您是否將部署設定在分割 (也稱為混合) 網域中，且該網域的某些使用者在內部部署中具有自己的主伺服器，而其他使用者則是透過線上環境中的主伺服器加以設定？**

設定各主題的詳細資訊。設定 [控制同盟使用者存取的原則](external-access-policies/configure-policies-to-control-federated-user-access.md)、 [啟用或停用同盟和公用 IM](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)連線，以及 [建立或編輯主控的 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)。


您可以設定外部使用者存取設定，包括任何您要用以控制外部使用者存取的原則，即使您並未啟用組織的外部使用者存取亦然。但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。當外部使用者存取停用，或未設定外部使用者存取原則加以支援時，外部使用者將無法與您組織的使用者通訊。

您的 Edge 部署會根據您設定 Edge 支援的方式，來驗證外部使用者 (但匿名使用者除外，匿名使用者是由當您建立會議並邀請參與者時，所傳送給匿名參與者的會議 ID 及密碼金鑰加以驗證) 的類型及控制存取。若要控制通訊，您可以設定一或多項原則並設定其他設定，以定義您部署內外之使用者彼此通訊的方式。這些原則及設定包括外部使用者存取的預設全域原則，以及您可以建立並設定以針對特定網站或使用者啟用一或多種外部使用者存取類型的網站與使用者原則。

