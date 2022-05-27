---
title: Lync Server 2013：管理同盟和外部存取商務用 Skype Server
ms.reviewer: ''
ms:assetid: 26f806c1-f284-4637-b06b-06270336c540
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520966(v=OCS.15)
ms:contentKeyID: 48183665
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 您可以啟用並設定外部使用者存取權，以控制支援的外部使用者是否可以與內部商務用 Skype Server使用者共同作業。
ms.openlocfilehash: c1bca3fe9b3d5e0189b03b3405d846601666d153
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676215"
---
# <a name="managing-federation-and-external-access-to-skype-for-business-server"></a>管理商務用 Skype Server 的同盟和外部存取

支援外部使用者的首要步驟，是部署 Edge Server 或 Edge 集區。 如需部署 Edge Server 的詳細資訊，請參閱[在 商務用 Skype Server 中部署 Edge Server](../../deploy/deploy-edge-server/deploy-edge-server.md)。

安裝並設定商務用 Skype Server的內部部署之後，組織中的內部使用者可以與其他在 Active Directory 網域服務 (AD DS) 中具有 SIP 帳戶的內部使用者共同作業。 共同作業可包含傳送和接收立即訊息，以及會議中目前狀態與參加情況的更新。 您可以啟用並設定外部使用者存取權，以控制支援的外部使用者是否可以與內部商務用 Skype Server使用者共同作業。 外部使用者可以包含部署的遠端使用者、同盟使用者 (包括公用立即訊息 (IM) 服務提供者) 的支援使用者，以及會議中的匿名參與者。

如果您的部署包含商務用 Skype Server Edge Server 或 Edge 集區，則可能的通訊類型範圍會大幅擴充。 有許多選項可供外部使用者存取、與其他 SIP 同盟網域的成員通訊，以及 SIP 同盟提供者。 設定 Edge Server 或 Edge 集區之後，您可以啟用外部使用者存取類型，並設定原則來控制外部存取。 在商務用 Skype Server中，您可以使用商務用 Skype Server 主控台、商務用 Skype Server管理[命令介面](../management-shell.md)或兩者來啟用和設定外部使用者存取和原則。

> [!IMPORTANT]
> 當您設計外部使用者存取的組態和原則時，必須知道原則的優先順序以及原則的套用方式。 商務用 Skype Server在一個原則層級套用的原則設定可以覆寫在另一個原則層級套用的設定。 商務用 Skype Server 原則優先順序為：使用者原則 (影響最大) 會覆寫網站原則，然後網站原則會覆寫全域原則 (影響最小)。 也就是說，原則設定愈接近原則影響的物件，對物件所造成的影響也越大。

根據預設，沒有任何原則支援外部使用者存取 (包括遠端使用者存取和同盟使用者存取) ，即使您已為組織啟用外部使用者存取支援也一樣。 若要控制外部使用者存取的使用，您必須設定一或多個原則。 在下列原則中，您會指定支援的外部使用者存取類型：

- **全域原則**：當您部署 Edge Server 時，會建立全域原則。 根據預設，全域原則中不會啟用任何外部使用者存取選項。 若要支援全域層級的外部使用者存取，您可以設定全域原則來支援一或多個外部使用者存取類型。 全域原則適用於組織中的所有使用者，但是網站原則和使用者原則會覆寫全域原則。 如果您刪除全域原則，不會將它移除。 而是會將它重設為預設值。

- **網站原則**：您可以建立並設定一或多個網站原則，以限制外部使用者對特定網站的存取支援。 月臺原則中的設定會覆寫全域原則，但僅限於網站原則所涵蓋的特定網站。 根據預設，網站原則會套用至該網站中的所有使用者，但會套用使用者原則來覆寫網站原則設定。

- **使用者原則**：您可以建立並設定一或多個使用者原則，以限制對特定使用者的遠端使用者存取支援。 使用者原則中的組態會覆寫全域和網站原則，但僅限於指派原則的特定使用者。 如果您建立使用者原則，必須將其套用至一或多個使用者，該原則才能生效。

若要決定需要建立或編輯哪些組態設定及原則，請參閱下列決策要點：

**您是否要允許您網域的內部及外部使用者能夠使用立即訊息、Web 會議及音訊/視訊來共同作業？**

如設定原則 [以控制遠端使用者](external-access-policies/configure-policies-to-control-remote-user-access.md)存取和 [啟用或停用同盟和公用 IM 聯](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)機主題所述，設定設定。

**您是否要允許匿名使用者加入您部署中使用者所主控的會議，以及收到該會議的邀請？**

如指 [派會議原則以支援匿名使用者](access-edge/assign-conferencing-policies-to-support-anonymous-users.md) 和 [建立會議](../conferencing/create-policies.md)原則主題中所述，設定設定。

**您是否要允許使用者與 SIP 同盟網域連絡人進行通訊？**

如設定原則 [以控制同盟使用者存取](external-access-policies/configure-policies-to-control-federated-user-access.md)、 [啟用或停用同盟和公用 IM 聯](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)機，以及 [管理組織的 SIP 同盟網域](sip-domains/manage-sip-federated-domains-for-your-organization.md)主題所述，設定設定。

**如果您已啟用與 SIP 同盟網域的通訊，是否要啟用 SIP 同盟自動探索？**

如啟用 [或停用同盟夥伴的探索](access-edge/enable-or-disable-discovery-of-federation-partners.md)主題中所述，設定設定。

**若您已啟用與 SIP 同盟網域的通訊，您是否還要啟用傳送免責聲明給同盟連絡人，以通知他們您使用了封裝功能，且可能會封裝通訊內容？**

如啟 [用或停用將封存免責聲明傳送給同盟合作夥伴主題中](access-edge/enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)所述，設定設定。

**您要允許使用者與啟用與公用提供者通訊的 SIP 同盟提供者通訊嗎？**

如設定原則[以控制公用使用者存取](external-access-policies/configure-policies-to-control-public-user-access.md)、[啟用或停用同盟和公用 IM 聯](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)機，以及[建立或編輯公用 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-public-sip-federated-providers-in-skype-for-business-server)主題所述，設定設定

**您要允許使用者與執行 Microsoft 365 或 Office 365 和 商務用 Skype Online 之託管提供者的 SIP 同盟提供者通訊嗎？**

如啟 [用或停用同盟和公用 IM 聯](access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 機和 [建立或編輯託管的 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)主題所述，設定設定。

**您是否將部署設定在分割 (也稱為混合) 網域中，且該網域的某些使用者在內部部署中具有自己的主伺服器，而其他使用者則是透過線上環境中的主伺服器加以設定？**

如設定原則 [以控制同盟使用者存取](external-access-policies/configure-policies-to-control-federated-user-access.md)、 [啟用或停用同盟和公用 IM 聯](access-edge/enable-or-disable-federation-and-public-im-connectivity.md)機，以及 [建立或編輯託管的 SIP 同盟提供者](sip-providers/manage-sip-federated-providers-for-your-organization.md#create-or-edit-hosted-sip-federated-providers-in-skype-for-business-server)主題所述，設定設定。

即使您尚未為組織啟用外部使用者存取權，您也可以設定外部使用者存取設定。 但只有在您啟用組織的外部使用者存取後，您所設定的原則與其他設定才會生效。 當外部使用者存取停用或未設定外部使用者存取原則來支援外部使用者存取原則時，外部使用者無法與您的使用者通訊。

邊緣部署會驗證外部使用者的類型，並根據您設定邊緣支援的方式來控制存取。 此規則的例外狀況是匿名使用者，這些使用者是由會議識別碼驗證，以及當您建立會議並邀請參與者時傳送給匿名參與者的通行金鑰。 若要控制通訊，您可以設定一或多個原則，以定義組織內外使用者彼此通訊的方式。 原則和設定包括您可以建立和設定的預設全域原則、網站原則和使用者原則。
