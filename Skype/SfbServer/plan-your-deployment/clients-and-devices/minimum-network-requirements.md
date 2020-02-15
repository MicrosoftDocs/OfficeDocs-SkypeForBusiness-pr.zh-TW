---
title: Skype 會議 App 的基本網路需求
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 摘要： 的組織不使用 Office 365 且需要存取執行動作的組織所主控的會議資訊。
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033187"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 會議 App 的基本網路需求
 
**摘要：** 組織不使用 Office 365 且需要存取執行動作的組織所主控的會議資訊。 本文不是這些應用程式的使用者。
  
若要允許使用者使用 Skype 會議 App 參加會議的商務用 Skype 中裝載，不使用 Office 365 的組織的網路系統管理員應該 whitelist 或以其他方式提供以下提及的 Fqdn、 IPs 及連接埠。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 會議 App 連線的需求

此處所列的資訊是[Office 365 Url 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)，可提供更多的深度，並會永遠是最新的子集。
                    
 
|應用程式 |目的地 Fqdn  |IP 位址  |連接埠  |
|---|---------|---------|---------|
|**Skype 會議 App** | \*。 lync.com <br/>\*。 infra.lync.com<br/>\*。 pipe.aria.microsoft.com<br/>\*。 sfbassets.com<br/>\*。 msecnd.net<br/>\*廣播<span></span>。 officeapps.live.com <br/>\*powerpoint<span></span>。 officeapps.live.com <br/>\*。 office.live.com<br/>\*。 cdn.office.net<br/>*.s microsoft.com<br/>        |   經常更新這些 IP 位址。  請參閱[Skype for Business IP 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)，以及[Office IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478 3481<br/>
|**Teams**    | \*<span></span>。 microsoft.com <br/>\*<span></span>。 skype.com | 經常更新這些 IP 位址。  請參閱[Skype for Business IP 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)，以及[Office IP 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478 3481

## <a name="see-also"></a>另請參閱
<a name="BKMK_Conferencing"> </a>

[規劃會議用戶端 （Web 應用程式和會議應用程式）](meetings-clients.md)

[為商務伺服器部署中用 Skype Web 可下載的用戶端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[支援的平台的 Skype 會議 App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
