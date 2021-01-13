---
title: Skype 會議 App 最低網路需求
ms.author: v-cichur
author: cichur
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
description: 摘要：針對未使用 Microsoft 365 或 Office 365 的組織提供的資訊，並且需要存取由此組織所主控的會議。
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816303"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Skype 會議 App 最低網路需求
 
**摘要：**  未使用 Microsoft 365 或 Office 365 的組織資訊，而且需要存取組織所主持的會議。 本文並非適用于這些應用程式的使用者。
  
若要讓使用者可以使用 Skype 會議應用程式來參加在商務用 Skype Online 中主控的會議，未使用 Microsoft 365 或 Office 365 之組織的網路系統管理員應該允許或以其他方式使用下列所述的 Fqdn、IPs 及埠。

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Skype 會議應用程式連線的需求

此處所列的資訊是 [Office 365 URLs 及 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)的子集，其提供更深入的深度，且一定會為最新。
                    
 
|應用程式 |目的地 Fqdn  |IP 位址  |連接埠  |
|---|---------|---------|---------|
|**Skype 會議 App** | \*。 lync.com <br/>\*。 infra.lync.com<br/>\*。 pipe.aria.microsoft.com<br/>\*。 sfbassets.com<br/>\*。 msecnd.net<br/>\*<span></span>officeapps.live.com <br/>\*<span></span>officeapps.live.com <br/>\*。 office.live.com<br/>\*。 cdn.office.net<br/>s-microsoft.com<br/>        |   這兩個 IP 位址經常更新。  請參閱 [商務用 SKYPE ip 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 和 [Office ip 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP： 80 &amp; 443<br/>UDP：3478-3481<br/>
|**Teams**    | \*<span></span>。 microsoft.com <br/>\*<span></span>。 skype.com | 這兩個 IP 位址經常更新。  請參閱 [商務用 SKYPE ip 範圍](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) 和 [Office ip 範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP：443 <br/> UDP：3478-3481

## <a name="see-also"></a>另請參閱
<a name="BKMK_Conferencing"> </a>

[規劃會議用戶端 (Web 應用程式和會議應用程式) ](meetings-clients.md)

[在商務用 Skype Server 中部署 Web 可下載的用戶端](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[支援的 Skype 會議應用程式平臺](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
