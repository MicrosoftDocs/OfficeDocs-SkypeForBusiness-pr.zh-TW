---
title: 新增 Edge Server FQDN
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
  - CSH
ms.custom:
  - ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
description: '您必須指定 Access Edge Service 的完整網域名稱 (FQDN)。 如果您未在 [選取功能] 頁面上選取 [使用單一 FQDN &amp; IP 位址] 選項，您也必須為 Web 會議 Edge service 和 A/V Edge service 指定 FQDN。'
---

# <a name="add-edge-server-fqdn"></a>新增 Edge Server FQDN
 
您必須指定 Access Edge Service 的完整網域名稱 (FQDN)。 如果您未在 [**選取功能**] 頁面上選取 [**使用單一 FQDN &amp; IP 位址**] 選項，您也必須為 Web 會議 Edge service 和 A/V Edge service 指定 FQDN。
  
此外，如果您選取 [ **使用單一 FQDN &amp; IP 位址** ] 選項，則必須為每個 Edge service 指定不同的埠號碼。 (建議的埠設定：444用於 Access edge service，8057用於 Web 會議 Edge service，而443用於 A/V Edge service) 。 如果您未選取該選項，可以為三個服務都使用相同的連接埠號碼 (例如 443)。
  

