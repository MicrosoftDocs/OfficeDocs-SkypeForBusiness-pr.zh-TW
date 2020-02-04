---
title: 新增 Director Web 服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: 基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。
ms.openlocfilehash: e62adfb080886397de51ff4c51c5fac19878eeff
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685316"
---
# <a name="add-director-web-service"></a>新增 Director Web 服務
 
基底 URL 是 URL 的 Web 服務身分識別，而不是 HTTPs://。 例如，如果該池的 Web 服務的完整 URL 是https://pool01.contoso.net，則基底 url 是 pool01.contoso.net。
  
如果您只部署單一控制器，就不能覆寫內部 Web 服務池的完整功能變數名稱（FQDN）。 如果您要為控制器池設定網域名稱系統（DNS）負載平衡，您可以指定不同的內部基底 URL （這必須與池 FQDN 不同，例如內部-\<您的基 url\>）。
  
您可以指定與內部基底 URL 不同的外部基底 URL，以區別網域命名。 例如，您的內部網域是 contoso.net，但是您的外部功能變數名稱是 contoso.com。 您可以使用 contoso.com 功能變數名稱定義外部基底 URL。 對於邊緣部署的反向 proxy 伺服器而言，這是很重要的。 外部基底 URL 網功能變數名稱稱應該與反向 proxy 的 FQDN 功能變數名稱相同。 
  

