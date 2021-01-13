---
title: 在商務用 Skype Server 中驗證 Edge 部署
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 摘要：瞭解如何驗證 Edge server 或 Edge Server 集區的部署在商務用 Skype Server 中是否正常運作。
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804353"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="bd94b-103">在商務用 Skype Server 中驗證 Edge 部署</span><span class="sxs-lookup"><span data-stu-id="bd94b-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="bd94b-104">**摘要：** 瞭解如何驗證 Edge server 或 Edge Server 集區的部署在商務用 Skype Server 中是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="bd94b-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="bd94b-105">部署 Edge Server 或 Edge Server 集區之後，您必須知道其是否運作正常。</span><span class="sxs-lookup"><span data-stu-id="bd94b-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="bd94b-106">以下是一些可協助您確認 Edge 環境連線至內部伺服器的專案，此外，您的外部使用者還是可以透過 Edge 連線到商務用 Skype Server 環境。</span><span class="sxs-lookup"><span data-stu-id="bd94b-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="bd94b-107">驗證內部伺服器和 Edge server 之間的連線能力</span><span class="sxs-lookup"><span data-stu-id="bd94b-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="bd94b-108">在安裝 Edge Server 時，會自動在 Edge Server 或 Edge Server 集區中進行連線驗證，但您仍然可以使用 Windows PowerShell 加以確認。</span><span class="sxs-lookup"><span data-stu-id="bd94b-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="bd94b-109">在具有中央管理存放區的內部伺服器上，或在已安裝 ( # A0) 之商務用 Skype Server 核心元件的任何已加入網域的電腦上執行 Get-CsManagementStoreReplicationStatus Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd94b-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="bd94b-110">執行這個命令的初始結果可能會提供錯誤狀態，而非 True 用於複寫。</span><span class="sxs-lookup"><span data-stu-id="bd94b-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="bd94b-111">如果發生這種情況，請執行 Invoke-CsManagementStoreReplication Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd94b-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="bd94b-112">請提供一些時間來完成複寫，然後再次執行 Get-CsManagementStoreReplicationStatus Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="bd94b-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="bd94b-113">驗證外部使用者的連線能力</span><span class="sxs-lookup"><span data-stu-id="bd94b-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="bd94b-114">我們確實有一個不錯的工具可以確認 Edge Server 設定，以及能夠為 Edge Server 案例連線、傳送及接收正確訊息的功能。</span><span class="sxs-lookup"><span data-stu-id="bd94b-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="bd94b-115">它是 [Remote Connectivity Anaylzer 網站](https://testconnectivity.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="bd94b-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="bd94b-116">這是由 Microsoft 支援人員所管理及維護的網站。</span><span class="sxs-lookup"><span data-stu-id="bd94b-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="bd94b-117">若要使用此工具，請流覽至網站，然後依照指示為您選擇適當的案例。</span><span class="sxs-lookup"><span data-stu-id="bd94b-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="bd94b-118">測試外部使用者連線時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="bd94b-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="bd94b-119">針對外部使用者存取的任何測試，都必須包含您組織所支援的每一種內部使用者類型，其中可能包含下列任何或所有專案：</span><span class="sxs-lookup"><span data-stu-id="bd94b-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="bd94b-120">至少一個同盟網域中的使用者 (我們建議您在) 進行測試。</span><span class="sxs-lookup"><span data-stu-id="bd94b-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="bd94b-121">匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="bd94b-121">Anonymous users.</span></span>
    
- <span data-ttu-id="bd94b-122">組織中遠端登入商務用 Skype 的使用者，但不會使用 VPN。</span><span class="sxs-lookup"><span data-stu-id="bd94b-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="bd94b-123">這些測試會判斷您的 Edge Server 是否為：</span><span class="sxs-lookup"><span data-stu-id="bd94b-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="bd94b-124">使用網路外部的 telnet 用戶端聆聽必要的連接埠。</span><span class="sxs-lookup"><span data-stu-id="bd94b-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="bd94b-125">例如： telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="bd94b-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="bd94b-126">您應該在 Edge Server 或 Edge Server 集區上，根據您的部署，對您所使用的埠執行上述測試。</span><span class="sxs-lookup"><span data-stu-id="bd94b-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="bd94b-127">執行準確的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="bd94b-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="bd94b-128">從您的網路外部，ping Edge Server 或 Edge Server 集區的每個外部 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="bd94b-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="bd94b-129">即使 ping 失敗，您也會看到 IP 位址，您可以比較先前指派的 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="bd94b-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

