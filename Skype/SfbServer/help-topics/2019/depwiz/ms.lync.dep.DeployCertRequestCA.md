---
title: 憑證要求 (憑證授權單位)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: 在 [選擇憑證授權單位 (CA)] 頁面上向線上憑證授權單位 (CA) (通常是您內部網路上的伺服器) 提出憑證申請時，您會看到兩個選項：
ms.openlocfilehash: 86da1e55cb43af86d28593dd8a76563b7d0a5a44
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692068"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="95314-103">憑證要求 (憑證授權單位)</span><span class="sxs-lookup"><span data-stu-id="95314-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="95314-104">在 [選擇憑證授權單位 (CA)]\*\*\*\* 頁面上向線上憑證授權單位 (CA) (通常是您內部網路上的伺服器) 提出憑證申請時，您會看到兩個選項：</span><span class="sxs-lookup"><span data-stu-id="95314-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="95314-105">從環境中偵測到的清單選取 CA。</span><span class="sxs-lookup"><span data-stu-id="95314-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="95314-106">指定另一個憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="95314-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="95314-107">如果您選取第一個選項，您會看到一個下拉式清單，其中包含在您的環境中偵測到的所有 Windows Server 認證授權機構。</span><span class="sxs-lookup"><span data-stu-id="95314-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="95314-108">選取適合您憑證的憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="95314-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="95314-109">您可能需要詢問 CA 系統管理員，以了解應該選擇的 CA。</span><span class="sxs-lookup"><span data-stu-id="95314-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="95314-p102">如果您選取第二個選項，請輸入憑證授權單位的完整網域名稱 (FQDN) 和 CA 執行個體，以用於您的憑證。如果您要使用的 CA 不是 Windows Server CA，則適合選取此選項，但 Windows Server CA 也適用。</span><span class="sxs-lookup"><span data-stu-id="95314-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="95314-112">請務必確認您需要具備的群組成員資格，以便成功提出憑證申請。</span><span class="sxs-lookup"><span data-stu-id="95314-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="95314-113">通常，憑證授權單位會根據在伺服器上安裝商務用 Skype Server 的需求，提供不同的許可權需求。</span><span class="sxs-lookup"><span data-stu-id="95314-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="95314-114">請向 CA 系統管理員確認申請憑證時的需求。</span><span class="sxs-lookup"><span data-stu-id="95314-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

