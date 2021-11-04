---
title: 新增前端 Web 服務
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 `https://pool01.contoso.net` ，則基底 url 是 `pool01.contoso.net` 。
ms.openlocfilehash: a02ab1d8c3013216c31d1e050e22eaf9cf614045
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60752132"
---
# <a name="add-front-end-web-services"></a>新增前端 Web 服務
 
基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 `https://pool01.contoso.net` ，則基底 url 是 `pool01.contoso.net` 。
  
您無法覆寫 Standard Edition Server 的內部 Web 服務集區完整網域名稱 (FQDN)。 若要設定網域名稱系統 (DNS) Enterprise Edition 前端集區的負載平衡，您可以指定不同的內部基礎 URL，其必須不同于集區 FQDN (例如內部- \<your base URL\>) 。
  
您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。 例如，您的內部網域是 `contoso.net` ，但您的外部功能變數名稱為 `contoso.com` 。 您會使用功能變數名稱定義外部基底 URL `contoso.com` 。 這對 Edge 部署的反向 Proxy 伺服器而言很重要。 外部基底 URL 網域名稱應該與反向 Proxy 的 FQDN 網域名稱相同。 立即訊息和目前狀態需要對前端集區的 HTTP 存取。
  

