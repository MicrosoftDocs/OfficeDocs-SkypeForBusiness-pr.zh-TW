---
title: 新增前端 Web 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。
ms.openlocfilehash: 10749cc746cf1f3d039a89fd351be6de77eafaee
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698198"
---
# <a name="add-front-end-web-services"></a>新增前端 Web 服務
 
基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。
  
您無法覆寫標準版伺服器的內部 Web 服務池完整功能變數名稱（FQDN）。 如果您要為企業版前端池設定網域名稱系統（DNS）負載平衡，您可以指定不同的內部基 URL，這種 URL 必須與 [池 FQDN] 不同（例如，內部-\<您的基本 URL\>）。
  
您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。 例如，您的內部網域是 contoso.net，但是您的外部功能變數名稱是 contoso.com。 您可以使用 contoso.com 功能變數名稱定義外部基底 URL。 對於邊緣部署的反向 proxy 伺服器而言，這是很重要的。 外部基底 URL 網功能變數名稱稱應該與反向 proxy 的 FQDN 功能變數名稱相同。 立即訊息和目前狀態需要對前端池的 HTTP 存取權。
  

