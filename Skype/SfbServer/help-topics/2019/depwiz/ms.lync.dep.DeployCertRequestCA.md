---
title: 簽署要求 (憑證授權單位)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 將憑證要求傳送到線上憑證授權單位單位 (CA 時)  (通常是內部網路上的伺服器) 上的 [選擇憑證授權單位單位 (CA) ] 頁面上，會顯示兩個選項：
ms.openlocfilehash: 8744471569c76e8f8196cda41ca398c48205fea8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830363"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="84d8e-103">簽署要求 (憑證授權單位)</span><span class="sxs-lookup"><span data-stu-id="84d8e-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="84d8e-104">將憑證要求傳送到線上憑證授權單位單位 (CA 時)  (通常是內部網路上的伺服器) 上的 [ **選擇憑證授權單位單位 (CA)** ] 頁面上，會顯示兩個選項：</span><span class="sxs-lookup"><span data-stu-id="84d8e-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="84d8e-105">從環境中偵測到的清單選取 CA。</span><span class="sxs-lookup"><span data-stu-id="84d8e-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="84d8e-106">指定另一個憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="84d8e-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="84d8e-107">如果您選取第一個選項，您會看到一個下拉式清單，其中包含在您的環境中偵測到的所有以 Windows Server 為基礎的憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="84d8e-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="84d8e-108">選取適合您憑證的憑證授權單位單位。</span><span class="sxs-lookup"><span data-stu-id="84d8e-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="84d8e-109">您可能需要與 CA 管理員協商，以瞭解選擇哪個 CA。</span><span class="sxs-lookup"><span data-stu-id="84d8e-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="84d8e-110">如果您選取第二個選項，請輸入您要用於憑證之憑證授權單位單位的完整功能變數名稱 (FQDN) 及 CA 實例。</span><span class="sxs-lookup"><span data-stu-id="84d8e-110">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate.</span></span> <span data-ttu-id="84d8e-111">如果您想要使用的 CA 不是以 Windows Server 為基礎的 CA，但適用于 Windows Server 型 ca，則此選項是適當的。</span><span class="sxs-lookup"><span data-stu-id="84d8e-111">This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="84d8e-112">請務必確認您需要成功使用憑證要求的群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="84d8e-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="84d8e-113">在伺服器上安裝商務用 Skype Server 的需求通常，憑證授權單位單位具有不同的許可權需求。</span><span class="sxs-lookup"><span data-stu-id="84d8e-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="84d8e-114">確認要求您的 CA 管理員要求憑證。</span><span class="sxs-lookup"><span data-stu-id="84d8e-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

