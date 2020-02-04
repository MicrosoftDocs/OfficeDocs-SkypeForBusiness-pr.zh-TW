---
title: 簽署要求 (憑證授權單位帳戶)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestCAAccount
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6251322d-ac36-4760-b467-bcd543af22aa
ROBOTS: NOINDEX, NOFOLLOW
description: 若要提交要求，您的憑證授權單位（CA）可能需要您目前登入的使用者以外的認證。
ms.openlocfilehash: 8319b18340d705645529dba93ccfab40a96b68a2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705678"
---
# <a name="certificate-request-certificate-authority-account"></a><span data-ttu-id="bea15-103">簽署要求 (憑證授權單位帳戶)</span><span class="sxs-lookup"><span data-stu-id="bea15-103">Certificate Request (Certificate Authority Account)</span></span>
 
<span data-ttu-id="bea15-104">若要提交要求，您的憑證授權單位（CA）可能需要您目前登入的使用者以外的認證。</span><span class="sxs-lookup"><span data-stu-id="bea15-104">To submit a request, your certification authority (CA) may require credentials other than the ones for the user that you are currently logged in as.</span></span> <span data-ttu-id="bea15-105">若要允許其他使用者使用證書申請，請選取 [為**憑證授權單位指定備用認證**] 核取方塊，然後輸入可要求_憑證的使用者_的使用者名稱或_功能變數名稱_\ 。</span><span class="sxs-lookup"><span data-stu-id="bea15-105">To allow a certificate request as a different user, select the check box **Specify alternate credentials for the certification authority**, and then type the user name or  _domain_\ _username_ for a user who can request the certificate.</span></span> <span data-ttu-id="bea15-106">在 [**密碼**] 文字方塊中，輸入您所指定之使用者的密碼。</span><span class="sxs-lookup"><span data-stu-id="bea15-106">In the **Password** text box, type the password for the user that you specified.</span></span> <span data-ttu-id="bea15-107">然後，使用者名稱和密碼就會作為證書申請程式的一部分，而不是在實際的憑證要求中傳送給線上 CA。</span><span class="sxs-lookup"><span data-stu-id="bea15-107">The user name and password are then sent as part of the certificate request process, but not in the actual certificate request, to an online CA.</span></span>
  

