---
title: 新增受信任的應用程式池 FQDN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: '若要定義受信任的應用程式池完整功能變數名稱 (FQDN), 請指定下列專案:'
ms.openlocfilehash: 026994a57da7838b2799484f000d69d8c9a168d7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188254"
---
# <a name="add-trusted-application-pool-fqdn"></a>新增受信任的應用程式池 FQDN
 
若要定義受信任的應用程式池完整功能變數名稱 (FQDN), 請指定下列專案:
  
將託管受信任之應用程式的伺服器或伺服器池的 FQDN。
  
如果您要為受信任的應用程式部署伺服器池以進行負載平衡和高可用性, 請選取 [**多個電腦池**], 或者如果您不需要負載平衡或高可用性, 請選取 [**單一電腦池**]。
  
> [!IMPORTANT]
> 一個受信任的應用程式伺服器稍後無法轉換為伺服器池。 如果您認為將來可能需要一個池, 您可以部署多個包含一部電腦的伺服器池, 並視需要新增伺服器。 
  
如需有關受信任的應用程式池的詳細資訊, 請參閱[新 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)。
  

