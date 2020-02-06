---
title: 憑證要求 (指定範本)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestTemplate
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d00ed98f-46f2-4367-b34c-513e5eafdd06
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以在 [指定備用憑證範本] 頁面上，定義預設使用的 Web 類型憑證範本以外的憑證範本。 選取 [針對所選的認證機構使用備用憑證範本] 核取方塊，然後在文字方塊憑證範本名稱中定義替換憑證範本的名稱。 您必須使用在憑證授權單位（CA）中定義的範本名稱。 按一下 [返回]，返回上一頁。 按一下 [取消] 以結束證書申請程式。
ms.openlocfilehash: a2ada69d4c71b44ea195ad65a991c6104bdb3443
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794402"
---
# <a name="certificate-request-specify-termplate"></a><span data-ttu-id="521c3-107">憑證要求 (指定範本)</span><span class="sxs-lookup"><span data-stu-id="521c3-107">Certificate Request (Specify Termplate)</span></span>
 
<span data-ttu-id="521c3-p102">[指定其他憑證範本]\*\*\*\* 頁面可讓您定義非預設使用之 WebServer 憑證範本的憑證範本。請選取 [將其他憑證範本用於所選的憑證授權單位]\*\*\*\* 核取方塊，然後在 [憑證範本名稱]\*\*\*\* 文字方塊中定義其他憑證範本的名稱。您所使用的範本名稱，必須與憑證授權單位 (CA) 中所定義的名稱相同。按 [上一步]\*\*\*\* 回到前一頁；按 [取消]\*\*\*\* 結束憑證要求程序。</span><span class="sxs-lookup"><span data-stu-id="521c3-p102">The **Specify Alternate Certificate Template** page enables you to define a certificate template other than the WebServer certificate template that is used by default. Select the check box **Use alternate certificate template for selected certification authority**, and then define the name of the alternate certificate template in the text box **Certificate template name**. You must use the name of the template as it is defined in the certification authority (CA). Click **Back** to go back to the previous page. Click **Cancel** to end the certificate request process.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="521c3-p103">唯有當公用 CA 建議您使用其系統上定義的特定範本來發出憑證時，才應該使用這個選項。如果憑證是由您的內部 CA 發出，您的 CA 系統管理員應該建議其他憑證範本使用什麼名稱。當您的組織已定義新的 WebServer 範本，且停用預設的 WebServer 範本時，這個選項極具價值。</span><span class="sxs-lookup"><span data-stu-id="521c3-p103">You should use this option only if you are advised by your public CA that you should use a specific template that is defined on their system for issuing certificates. If the certificate is being issued by your internal CA, your CA administrator should advise you what name to use for the alternate certificate template. This option is extremely valuable in cases where your organization has defined a new WebServer template and has disabled the default WebServer template.</span></span> 
  

