---
title: 避免服務的會話
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以使用舊版安裝控制台, 避免在特定電腦上執行所有舊版服務的新會話, 或避免特定舊版服務的新會話。
ms.openlocfilehash: 978c97bd7f610e6b40d467b80f5df8483b6d370f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244576"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="e9515-103">避免服務的會話</span><span class="sxs-lookup"><span data-stu-id="e9515-103">Prevent sessions for services</span></span>

<span data-ttu-id="e9515-104">您可以使用舊版安裝控制台, 避免在特定電腦上執行所有舊版服務的新會話, 或避免特定舊版服務的新會話。</span><span class="sxs-lookup"><span data-stu-id="e9515-104">You can use the legacy installs Control Panel to prevent new sessions for all the legacy services running on a specific computer or to prevent new sessions for a specific legacy service.</span></span>
  
## <a name="to-prevent-new-sessions-for-services-on-a-computer"></a><span data-ttu-id="e9515-105">若要避免在電腦上使用新的服務會話</span><span class="sxs-lookup"><span data-stu-id="e9515-105">To prevent new sessions for services on a computer</span></span>

1. <span data-ttu-id="e9515-106">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦2019。</span><span class="sxs-lookup"><span data-stu-id="e9515-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="e9515-107">開啟商務用 Skype 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e9515-107">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="e9515-108">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-108">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="e9515-109">在 [**狀態**] 頁面上, 視需要排序或搜尋清單, 以尋找執行您想要防止新會話之服務的電腦, 然後按一下該電腦。</span><span class="sxs-lookup"><span data-stu-id="e9515-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span> 
    
5. <span data-ttu-id="e9515-110">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-110">Click **Action**.</span></span>
    
6. <span data-ttu-id="e9515-111">按一下 [**防止所有服務的新會話**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-111">Click **Prevent new sessions for all services**.</span></span>
    
## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="e9515-112">若要防止特定服務的新會話</span><span class="sxs-lookup"><span data-stu-id="e9515-112">To prevent new sessions for a specific service</span></span>

1. <span data-ttu-id="e9515-113">從屬於 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權利), 或指派給 CsServerAdministrator 或 CsAdministrator 角色, 登入您在其中部署商務用 Skype Server 的網路中的任何電腦2019。</span><span class="sxs-lookup"><span data-stu-id="e9515-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2019.</span></span>
    
2. <span data-ttu-id="e9515-114">開啟商務用 Skype 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="e9515-114">Open Skype for Business Control Panel.</span></span>
    
3. <span data-ttu-id="e9515-115">在左側導覽列中, 按一下 [**拓撲**], 然後按一下 [**狀態**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-115">In the left navigation bar, click **Topology**, and then click **Status**.</span></span>
    
4. <span data-ttu-id="e9515-116">在 [**狀態**] 頁面上, 視需要排序或搜尋清單, 以尋找執行您要開始或停止之服務的電腦, 然後按一下它。</span><span class="sxs-lookup"><span data-stu-id="e9515-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span> 
    
5. <span data-ttu-id="e9515-117">按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-117">Click **Properties**.</span></span>
    
6. <span data-ttu-id="e9515-118">如有需要, 請排序服務清單, 然後按一下您要防止新會話的服務。</span><span class="sxs-lookup"><span data-stu-id="e9515-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>
    
7. <span data-ttu-id="e9515-119">按一下 [**動作**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-119">Click **Action**.</span></span>
    
8. <span data-ttu-id="e9515-120">按一下 [**避免新的服務會話**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-120">Click **Prevent new sessions for service**.</span></span>
    
9. <span data-ttu-id="e9515-121">按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e9515-121">Click **Close**.</span></span>
    

