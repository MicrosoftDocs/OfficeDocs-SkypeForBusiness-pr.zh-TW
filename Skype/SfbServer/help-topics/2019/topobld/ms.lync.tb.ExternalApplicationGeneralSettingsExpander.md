---
title: 外部應用程式一般設定展開工具
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.ExternalApplicationGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa7268ac-b9e3-4d25-bff4-e59d305120f2
ROBOTS: NOINDEX, NOFOLLOW
description: 若要編輯已定義之受信任的應用程式伺服器的屬性，請遵循下列指示進行。
ms.openlocfilehash: eacc0c854290fcf24196a8e4c58829231dc725c4
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793741"
---
# <a name="external-application-general-settings-expander"></a><span data-ttu-id="ba86e-103">外部應用程式一般設定展開工具</span><span class="sxs-lookup"><span data-stu-id="ba86e-103">External Application General Settings Expander</span></span>
 
<span data-ttu-id="ba86e-104">若要編輯已定義之受信任的應用程式伺服器的屬性，請遵循下列指示進行。</span><span class="sxs-lookup"><span data-stu-id="ba86e-104">To edit the properties for a trusted application server that has already been defined, follow these instructions.</span></span>
  
<span data-ttu-id="ba86e-105">您可以修改兩個區段：</span><span class="sxs-lookup"><span data-stu-id="ba86e-105">There are two sections that you can modify:</span></span>
  
> <span data-ttu-id="ba86e-106">一般設定</span><span class="sxs-lookup"><span data-stu-id="ba86e-106">General settings</span></span>
> 
> <span data-ttu-id="ba86e-107">下一個躍點設定</span><span class="sxs-lookup"><span data-stu-id="ba86e-107">Next hop settings</span></span>
    
## <a name="general-settings"></a><span data-ttu-id="ba86e-108">一般設定</span><span class="sxs-lookup"><span data-stu-id="ba86e-108">General Settings</span></span>

<span data-ttu-id="ba86e-109">您可以修改受信任的應用程式伺服器池目前的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="ba86e-109">You can modify the current fully qualified domain name (FQDN) for the trusted application server pool.</span></span> <span data-ttu-id="ba86e-110">編輯 [池 FQDN] 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ba86e-110">Edit the name of the pool FQDN.</span></span> <span data-ttu-id="ba86e-111">網功能變數名稱稱系統（DNS）主機（A）記錄必須存在於新專案中，才能讓用戶端或伺服器連線至新的 [池名稱]。</span><span class="sxs-lookup"><span data-stu-id="ba86e-111">The Domain Name System (DNS) host (A) records must exist for the new entry before clients or servers can connect to the new pool name.</span></span>
  
<span data-ttu-id="ba86e-112">如果您需要將配置資料複製到此池中，請選取 [**啟用將配置資料複製到這個資料集**]。</span><span class="sxs-lookup"><span data-stu-id="ba86e-112">Select **Enable replication of configuration data to this pool** if you need to have replication of configuration data to this pool.</span></span> <span data-ttu-id="ba86e-113">如果您不想要複製配置資料，請清除核取符號。</span><span class="sxs-lookup"><span data-stu-id="ba86e-113">Clear the check mark if you do not want to replicate the configuration data.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="ba86e-114">下一個躍點設定</span><span class="sxs-lookup"><span data-stu-id="ba86e-114">Next Hop Settings</span></span>

<span data-ttu-id="ba86e-115">您可以從下拉式清單中選取已定義的企業版 [前端] 池或 [標準版版本前端伺服器]，以指定受信任的應用程式伺服器池的下一個躍點伺服器。</span><span class="sxs-lookup"><span data-stu-id="ba86e-115">You can specify the trusted application server pool's next hop server by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="ba86e-116">控制器或主管池不是受信任之應用程式伺服器下個躍點的有效選取範圍，且不會出現在清單中。</span><span class="sxs-lookup"><span data-stu-id="ba86e-116">A Director or Director pool is not a valid selection for a trusted application server next hop and will not appear in the list.</span></span>
  

<span data-ttu-id="ba86e-117">按一下 **[確定]** 接受並儲存您的變更。</span><span class="sxs-lookup"><span data-stu-id="ba86e-117">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="ba86e-118">按一下 [取消]\*\*\*\* 捨棄變更並結束內容頁面。</span><span class="sxs-lookup"><span data-stu-id="ba86e-118">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  

