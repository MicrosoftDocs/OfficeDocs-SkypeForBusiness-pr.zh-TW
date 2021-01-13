---
title: 新增信任的應用程式集區 FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要為信任的應用程式集區定義完整網域名稱 (FQDN)，請指定下列設定：
ms.openlocfilehash: e34c3ba68a90e292da9441465d9077112b1ce173
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811813"
---
# <a name="add-trusted-application-pool-fqdn"></a>新增信任的應用程式集區 FQDN
 
若要為信任的應用程式集區定義完整網域名稱 (FQDN)，請指定下列設定：
  
將裝載信任的應用程式的伺服器或伺服器集區的 FQDN。
  
如果要從負載平衡和高可用性部署信任的應用程式的伺服器集區，請選取 [多部電腦集區]，或者，如果您不需要負載平衡或高可用性，請選取 [單一電腦集區]。
  
> [!IMPORTANT]
> 之後無法將單一信任的應用程式伺服器轉換為伺服器集區。如果您認為未來可能需要集區，您現在可以部署含單一電腦的多個伺服器集區，需要時再新增伺服器。 
  
如需信任的應用程式集區的詳細資訊，請參閱＜[New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)＞。
  

