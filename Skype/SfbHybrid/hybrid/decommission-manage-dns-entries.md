---
title: 在解除委任您的內部部署環境時管理 DNS 專案
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 解除委任內部部署商務用 Skype 環境時，如何管理 DNS 專案的指示。
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458986"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a>更新 DNS 專案，讓您的組織全部 Teams

先前部署商務用 Skype Server 或 Lync Server 的內部部署組織可能仍然具有指向內部部署商務用 Skype 部署的 DNS 專案。 如果您的組織包括內部部署商務用 Skype 使用者，這些記錄就是必要的。 不過，如果您的組織不再有任何內部部署商務用 Skype 或 Lync Server 使用者，這些記錄就不再是必要的。 實際上，在完成從內部部署至 Teams 的遷移時，必須更新這些記錄，使其指向 Microsoft 365 或移除。 Microsoft 無法為您採取此步驟。

當您嘗試將 TeamsOnly 授與整個租使用者時，Teams 會檢查 DNS，判斷您的組織是否存在這些 dns 記錄中的任何記錄。 如果找到任何記錄，且其指向 Microsoft 365 以外的專案，則嘗試將租使用者共存模式變更為 TeamsOnly 時，會因設計而失敗。 這種設計是為了避免使用內部部署使用者的混合式組織誤將 TeamsOnly 模式套用到租使用者--因為這樣做會中斷任何內部部署商務用 Skype 使用者的同盟 (是否使用 Teams 或商務用 Skype) 。

此外，這些記錄必須更新，讓您可以將 TeamsOnly 授與整個承租人。

> [!Note] 
> 在極少的情況下，將 DNS 設定為組織的內部部署與 Microsoft 365，可能會造成其他一些組織的同盟停止運作，直到其他組織更新其同盟設定為止：
>
> - 任何使用舊版直接同盟模型的同盟組織 (又稱為允許的夥伴伺服器) ，都必須更新其組織的允許網域專案，以移除 proxy FQDN。 這種舊版同盟模型不是以 DNS SRV 記錄為基礎，因此當您的組織移至雲端時，此設定將會到期。
> 
> - 任何沒有啟用 sipfed <span> 之主機服務提供者的同盟組織。com 必須更新其設定，才能啟用該功能。 只有在同盟組織完全存在於內部部署，且決不會與任何混合式或線上租使用者同盟的情況下，才可能出現這種情況。 在此情況下，與這些組織的同盟必須啟用其主機服務提供者後，才能運作。
>
> 如果您懷疑任何同盟協力廠商可能使用的是直接同盟或尚未與任何線上或混合組織同盟，我們建議您在準備完成對雲端的遷移時，向他們傳送此資訊的通訊。

## <a name="how-to-identify-stale-dns-records"></a>如何識別陳舊的 DNS 記錄

若要識別任何防止您的組織成為所有 Teams 的 DNS 記錄，您可以使用 Teams 系統管理中心，將共存模式變更為 TeamsOnly。 移至 **全組織設定**  ->  **Teams 升級**。 任何阻止組織成為 Teams 的 DNS 記錄，都將會包含在錯誤訊息中。  在事件中找不到 DNS 記錄時，您的組織的共存模式將變更為 TeamsOnly。 

## <a name="how-to-remove-stale-dns-records"></a>如何移除過時的 DNS 記錄

如果您的組織已沒有任何內部部署商務用 Skype Server 或 Lync Server 使用者，您必須執行下列動作：

- 更新商務用 Skype DNS 記錄，以指向 Microsoft 365 (而非內部部署) 。

- 如果不再使用 SIP 網域，請移除商務用 Skype DNS 記錄。 

在每個可找到下列記錄的網域中，更新這些記錄，如下所示：

| Record type (記錄類型) | 名稱 | TTL | Priority (優先順序) | Weight (權數) | Port (連接埠) | Value (值) |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| SRV | _sipfederationtls tcp | 3600 |  100 | 1  | 5061  | sipfed.online.lync.com |
| SRV | _sip tls | 3600  | 100 |    1    | 443   | sipdir.online.lync.com |
| CNAME | lyncdiscover |    3600 |  不適用 |   不適用 |   不適用 |   webdir.online.lync.com |
| CNAME |   sip | 3600 |    不適用 |   不適用  | 不適用 |    sipdir.online.lync.com |
|||||||




