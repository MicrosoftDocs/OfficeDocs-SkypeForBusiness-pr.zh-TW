---
title: Skype 會議 App 最低網路需求
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
description: 摘要：適用于不使用 Office 365 的組織，且需要存取由此組織託管的會議的資訊。
ms.openlocfilehash: e158d93b68df761b59535f4e9239d14194c10443
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816022"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 會議 App 最低網路需求
 
**摘要：** 針對沒有使用 Office 365 且需要存取組織所託管之會議的組織的資訊。 本文不適用於這些 app 的使用者。
  
若要允許使用者使用 Skype 會議應用程式來出席在商務用 Skype Online 中託管的會議，不使用 Office 365 之組織的網路系統管理員應該白名單，或以其他方式提供 Fqdn、Ip 及下列埠（如下所述）。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 會議應用程式連線的需求

此處所列的資訊是[Office 365 url 和 IP 位址範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)的子集，提供更多的深度，且總保持最新狀態。
                    
 
|適用 |目的地 Fqdn  |IP 位址  |埠  |
|---|---------|---------|---------|
|**Skype 會議應用程式** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*<span> </span>officeapps.live.com <br/>\*<span> </span>officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   這些 IP 位址會經常更新。  請參閱[商務用 SKYPE ip 範圍](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)以及[Office IP 範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP： 80 &amp; 443<br/>UDP：3478-3481<br/>
|**團隊**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | 這些 IP 位址會經常更新。  請參閱[商務用 SKYPE ip 範圍](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip)以及[Office IP 範圍](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP：443 <br/> UDP：3478-3481

## <a name="see-also"></a>另請參閱
<a name="BKMK_Conferencing"> </a>

[規劃會議用戶端（Web App 與會議應用程式）](meetings-clients.md)

[在商務用 Skype Server 中部署網頁下載用戶端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Skype 會議應用程式的支援平臺](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
