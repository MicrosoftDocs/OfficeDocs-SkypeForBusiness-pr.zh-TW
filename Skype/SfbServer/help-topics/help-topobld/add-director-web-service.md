---
title: 新增 Director Web 服務
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 `https://pool01.contoso.net` ，則基底 url 是 `pool01.contoso.net` 。
ms.openlocfilehash: 26e7056e670225aabf812bfe9dc782d800325757
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863980"
---
# <a name="add-director-web-service"></a>新增 Director Web 服務
 
基底 URL 是 URL 的 Web 服務識別身分，去除 https://。 例如，如果集區的 Web 服務完整 URL 為 `https://pool01.contoso.net` ，則基底 url 是 `pool01.contoso.net` 。
  
如果您只有部署一台 Director，將無法覆寫內部 Web 服務的集區完整網域名稱 (FQDN)。 若要設定網域名稱系統 (DNS) Director 集區的負載平衡，您可以指定不同的內部基底 URL (（該 URL 必須與集區 FQDN 不同），而且可以是內部) （如內部 \<your base URL\> ）。
  
您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。 例如，您的內部網域是 `contoso.net` ，但您的外部功能變數名稱為 `contoso.com` 。 您可以使用功能變數名稱定義外部基底 URL `contoso.com` 。 這對 Edge 部署的反向 Proxy 伺服器而言很重要。 外部基底 URL 網域名稱應該與反向 Proxy 的 FQDN 網域名稱相同。 
  

