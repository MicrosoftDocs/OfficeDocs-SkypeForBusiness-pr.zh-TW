---
title: 憑證要求 (憑證授權帳戶)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCAAccount
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: 若要送出要求，憑證授權單位 (CA) 可能會要求不同於目前用來登入之使用者身分的認證。
ms.openlocfilehash: ab3e5f1d15b32e866a0a8a99f54ce8a1b3d81a42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830343"
---
# <a name="certificate-request-certificate-authority-account"></a><span data-ttu-id="39a66-103">憑證要求 (憑證授權帳戶)</span><span class="sxs-lookup"><span data-stu-id="39a66-103">Certificate Request (Certificate Authority Account)</span></span>
 
<span data-ttu-id="39a66-104">若要送出要求，憑證授權單位 (CA) 可能會要求不同於目前用來登入之使用者身分的認證。</span><span class="sxs-lookup"><span data-stu-id="39a66-104">To submit a request, your certification authority (CA) may require credentials other than the ones for the user that you are currently logged in as.</span></span> <span data-ttu-id="39a66-105">若要允許憑證要求為不同的使用者，請選取 [為 **憑證授權單位單位指定替代認證**] 核取方塊，然後輸入可要求憑證之使用者的使用者名稱或 _網域_ 使用者名稱 \   。</span><span class="sxs-lookup"><span data-stu-id="39a66-105">To allow a certificate request as a different user, select the check box **Specify alternate credentials for the certification authority**, and then type the user name or  _domain_\ _username_ for a user who can request the certificate.</span></span> <span data-ttu-id="39a66-106">在 [密碼] 文字方塊中，輸入您指定的使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="39a66-106">In the **Password** text box, type the password for the user that you specified.</span></span> <span data-ttu-id="39a66-107">然後，憑證要求程序中 (而不是在實際憑證要求中) 便會將使用者名稱和密碼傳送至線上 CA。</span><span class="sxs-lookup"><span data-stu-id="39a66-107">The user name and password are then sent as part of the certificate request process, but not in the actual certificate request, to an online CA.</span></span>
  

