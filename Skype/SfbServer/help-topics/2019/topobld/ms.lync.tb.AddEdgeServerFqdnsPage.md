---
title: 新增 Edge Server FQDN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerFqdnsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 84a9511d-601d-4819-a30c-7b08d96e4d97
ROBOTS: NOINDEX, NOFOLLOW
description: 您必須指定 Access Edge Service 的完整網域名稱 (FQDN)。 如果您未 &amp; 在 [選取功能] 頁面上選取 [使用單一 FQDN IP 位址] 選項，您也必須為 Web 會議 Edge service 和 A/V Edge service 指定 FQDN。
ms.openlocfilehash: b54e496ca90372c815b850bf87800e73dd354a11
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835923"
---
# <a name="add-edge-server-fqdn"></a><span data-ttu-id="ca4f3-104">新增 Edge Server FQDN</span><span class="sxs-lookup"><span data-stu-id="ca4f3-104">Add Edge Server FQDN</span></span>
 
<span data-ttu-id="ca4f3-105">您必須指定 Access Edge Service 的完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="ca4f3-105">You must specify a fully qualified domain name (FQDN) for the Access Edge service.</span></span> <span data-ttu-id="ca4f3-106">如果您未在 [**選取功能**] 頁面上選取 [**使用單一 FQDN &amp; IP 位址**] 選項，您也必須為 Web 會議 Edge service 和 A/V Edge service 指定 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ca4f3-106">If you did not select the **Use a single FQDN &amp; IP address** option on the **Select features** page, you must also specify an FQDN for the Web Conferencing Edge service and for the A/V Edge service.</span></span>
  
<span data-ttu-id="ca4f3-107">此外，如果您選取 [ **使用單一 FQDN &amp; IP 位址** ] 選項，則必須為每個 Edge service 指定不同的埠號碼。 (建議的埠設定：444用於 Access edge service，8057用於 Web 會議 Edge service，而443用於 A/V Edge service) 。</span><span class="sxs-lookup"><span data-stu-id="ca4f3-107">Also, if you selected the **Use a single FQDN &amp; IP address** option, you must specify a different port number for each of the Edge services (recommended port settings: 444 for Access Edge service, 8057 for Web Conferencing Edge service, and 443 for A/V Edge service).</span></span> <span data-ttu-id="ca4f3-108">如果您未選取該選項，可以為三個服務都使用相同的連接埠號碼 (例如 443)。</span><span class="sxs-lookup"><span data-stu-id="ca4f3-108">If you did not select the option, you can use the same port number (such as 443) for all three services.</span></span>
  

