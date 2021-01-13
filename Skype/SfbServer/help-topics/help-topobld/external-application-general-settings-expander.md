---
title: 外部應用程式一般設定展開工具
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
description: 若要編輯已定義之信任的應用程式伺服器的屬性，請遵循下列指示。
ms.openlocfilehash: 55f6bfee68370f8f341080e54953120e48f628f8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804763"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="5eab8-103">外部應用程式一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="5eab8-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="5eab8-104">若要編輯已定義之信任的應用程式伺服器的屬性，請遵循下列指示。</span><span class="sxs-lookup"><span data-stu-id="5eab8-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="5eab8-105">您可以修改兩個區段：</span><span class="sxs-lookup"><span data-stu-id="5eab8-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="5eab8-106">一般設定</span><span class="sxs-lookup"><span data-stu-id="5eab8-106">General settings</span></span>
> 
> <span data-ttu-id="5eab8-107">下一個躍點設定</span><span class="sxs-lookup"><span data-stu-id="5eab8-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="5eab8-108">一般設定</span><span class="sxs-lookup"><span data-stu-id="5eab8-108">General Settings</span></span>

<span data-ttu-id="5eab8-p101">您可以修改信任的應用程式伺服器集區目前的完整網域名稱 (FQDN)。編輯集區 FQDN 的名稱。新的項目必須有網域名稱系統 (DNS) 主機 (A) 記錄，用戶端或伺服器才能連線至新的集區名稱。</span><span class="sxs-lookup"><span data-stu-id="5eab8-p101">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool. Edit the name of the pool FQDN. The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="5eab8-p102">如果您需要將組態資料複寫至此集區，請選取 **[對此集區啟用組態資料的複寫]**。如果您不要複寫組態資料，請清除核取記號。</span><span class="sxs-lookup"><span data-stu-id="5eab8-p102">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool. Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="5eab8-114">下一個躍點設定</span><span class="sxs-lookup"><span data-stu-id="5eab8-114">Next Hop Settings</span></span>

<span data-ttu-id="5eab8-115">您可以從下拉式清單中選取 [定義的 Enterprise Edition 前端集區] 或 [Standard Edition 前端伺服器]，以指定信任的應用程式伺服器集區的下一個躍點伺服器。</span><span class="sxs-lookup"><span data-stu-id="5eab8-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="5eab8-116">Director 或 Director 集區不能作為信任的應用程式伺服器下一個躍點，因此不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="5eab8-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  


<span data-ttu-id="5eab8-117">按一下 **[確定]** 以接受並儲存變更。</span><span class="sxs-lookup"><span data-stu-id="5eab8-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="5eab8-118">按一下 **[取消]** 捨棄變更並結束內容頁面。</span><span class="sxs-lookup"><span data-stu-id="5eab8-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

