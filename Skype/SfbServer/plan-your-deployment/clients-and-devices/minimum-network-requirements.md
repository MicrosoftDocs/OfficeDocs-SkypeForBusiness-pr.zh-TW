---
title: Skype 會議 App 最低網路需求
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要：不使用Microsoft 365或Office 365且需要存取由組織主持會議的組織資訊。
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674525"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 會議 App 最低網路需求

**總結：** 不使用Microsoft 365或Office 365且需要存取由組織主持會議的組織資訊。 本文不適用於Office 365或Microsoft 365使用者。

組織中未使用Microsoft 365或Office 365的Skype會議應用程式使用者可能需要參加 商務用 Skype Online 中託管的會議。 若要參加這些會議，其網路系統管理員必須允許下列 FQDN、IP 位址和埠通過其防火牆。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype會議應用程式連線能力的需求

此處所列的資訊是[Office 365 URL 和 IP 位址範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)中資訊的子集。 該主題更深入，而且永遠都是最新的。

|應用程式|目的地 FQDN|IP 位址|連接埠|
|---|---------|---------|---------|
|**Skype會議應用程式**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com <span></span> <br/>\*powerpoint.officeapps.live.com <span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|這些 IP 位址經常更新。 請[參閱商務用 Skype和Microsoft Teams IP 範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)以及[Office IP 範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP：80 & 443<br/>UDP：3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|這些 IP 位址經常更新。 請[參閱商務用 Skype和Microsoft Teams IP 範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)以及[Office IP 範圍](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP：443 <br/> UDP：3478-3481|

## <a name="see-also"></a>另請參閱
<a name="BKMK_Conferencing"> </a>

[規劃 Web 應用程式和會議應用程式 (會議用戶端) ](meetings-clients.md)

[在 商務用 Skype Server 中部署 Web 可下載用戶端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[支援Skype會議應用程式的平臺](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
