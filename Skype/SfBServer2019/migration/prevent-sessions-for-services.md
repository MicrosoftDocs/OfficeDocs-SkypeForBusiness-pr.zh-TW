---
title: 防止服務的工作階段
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 您可以使用舊版安裝控制台，以防止在特定電腦上執行的所有舊版服務的新會話，或阻止特定舊版服務的新會話。
ms.openlocfilehash: c5cc8846febaf690376e01c36b9fa023b8377970
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752285"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="a9869-103">防止服務的工作階段</span><span class="sxs-lookup"><span data-stu-id="a9869-103">Prevent sessions for services</span></span>

<span data-ttu-id="a9869-104">您可以使用舊版安裝控制台，以防止在特定電腦上執行的所有舊版服務的新會話，或阻止特定舊版服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="a9869-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="a9869-105">若要防止電腦上的服務的新會話</span><span class="sxs-lookup"><span data-stu-id="a9869-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="a9869-106">從 RTCUniversalServerAdmins 群組成員的使用者帳戶（或具有同等的使用者權限），或是指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 2019 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a9869-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="a9869-107">開啟商務用 Skype 控制台。</span><span class="sxs-lookup"><span data-stu-id="a9869-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="a9869-108">在左導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="a9869-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="a9869-109">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要阻止新工作階段之服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="a9869-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="a9869-110">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="a9869-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="a9869-111">按一下 **[阻止對所有服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="a9869-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="a9869-112">阻止特定服務的新工作階段</span><span class="sxs-lookup"><span data-stu-id="a9869-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="a9869-113">從 RTCUniversalServerAdmins 群組成員的使用者帳戶（或具有同等的使用者權限），或是指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您部署商務用 Skype Server 2019 的網路中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="a9869-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="a9869-114">開啟商務用 Skype 控制台。</span><span class="sxs-lookup"><span data-stu-id="a9869-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="a9869-115">在左導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="a9869-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="a9869-116">在 **[狀態]** 頁面上，視需要排序或搜尋整個清單，以尋找目前正在執行您想要啟動或停止服務的電腦，然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="a9869-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="a9869-117">按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="a9869-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="a9869-118">視需要排序服務清單，然後按一下要阻止新工作階段的服務。</span><span class="sxs-lookup"><span data-stu-id="a9869-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="a9869-119">按一下 **[動作]**。</span><span class="sxs-lookup"><span data-stu-id="a9869-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="a9869-120">按一下 **[阻止對服務的新工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="a9869-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="a9869-121">按一下 **[關閉]**。</span><span class="sxs-lookup"><span data-stu-id="a9869-121">Click **Close**.</span></span>
    

