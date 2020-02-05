---
title: 驗證您在商務用 Skype Server 中的邊緣部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：瞭解如何確認您的 Edge 伺服器或 Edge 伺服器池部署在商務用 Skype Server 中是否正常運作。
ms.openlocfilehash: c73b77fd0171afe20f9e40b48c47ef4304df4c66
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768296"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="830bc-103">驗證您在商務用 Skype Server 中的邊緣部署</span><span class="sxs-lookup"><span data-stu-id="830bc-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="830bc-104">**摘要：** 瞭解如何確認您的 Edge 伺服器或 Edge 伺服器池部署在商務用 Skype Server 中是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="830bc-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="830bc-105">部署 Edge 伺服器或 Edge 伺服器池之後，您必須知道它是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="830bc-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="830bc-106">以下是一些可協助您確認 Edge 環境與內部伺服器連線的情況，而且您的外部使用者也可以透過您的邊緣連線到您的商務用 Skype Server 環境。</span><span class="sxs-lookup"><span data-stu-id="830bc-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="830bc-107">驗證內部伺服器與邊緣伺服器之間的連線性</span><span class="sxs-lookup"><span data-stu-id="830bc-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="830bc-108">當安裝邊緣伺服器時，在 Edge 伺服器或 Edge 伺服器池中自動進行連線驗證，您仍然可以使用 Windows PowerShell 確認此操作。</span><span class="sxs-lookup"><span data-stu-id="830bc-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="830bc-109">在具有中央管理存儲的內部伺服器上執行 CsManagementStoreReplicationStatus Cmdlet，或在已安裝商務用 Skype Server Core 元件（OcsCore .msi）的已加入網域的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="830bc-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="830bc-110">執行此命令的初始結果可能會為複製提供 False 狀態，而不是 True。</span><span class="sxs-lookup"><span data-stu-id="830bc-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="830bc-111">如果發生這種情況，請執行 CsManagementStoreReplication Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="830bc-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="830bc-112">請提供一些時間來完成複製，然後再次執行 CsManagementStoreReplicationStatus Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="830bc-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="830bc-113">驗證外部使用者的連線性</span><span class="sxs-lookup"><span data-stu-id="830bc-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="830bc-114">我們有一個不錯的工具，可用於確認 Edge 伺服器設定，以及能夠連線、傳送及接收邊緣伺服器案例的正確訊息。</span><span class="sxs-lookup"><span data-stu-id="830bc-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="830bc-115">這是[遠端連線 Anaylzer 的網站](https://testconnectivity.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="830bc-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="830bc-116">這是由 Microsoft 支援服務管理和維護的網站。</span><span class="sxs-lookup"><span data-stu-id="830bc-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="830bc-117">若要使用此工具，請流覽至該網站，然後依照指示選擇適合您的案例。</span><span class="sxs-lookup"><span data-stu-id="830bc-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="830bc-118">測試外部使用者連線性時的考慮事項</span><span class="sxs-lookup"><span data-stu-id="830bc-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="830bc-119">針對外部使用者存取的任何測試，都必須包含貴組織支援的每一種內部使用者類型，其中可能包含下列任一或所有專案：</span><span class="sxs-lookup"><span data-stu-id="830bc-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="830bc-120">至少一個聯盟網域中的使用者（我們建議您將它們全部測試）。</span><span class="sxs-lookup"><span data-stu-id="830bc-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="830bc-121">匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="830bc-121">Anonymous users.</span></span>
    
- <span data-ttu-id="830bc-122">貴組織中已登入商務用 Skype 但無法使用 VPN 的使用者。</span><span class="sxs-lookup"><span data-stu-id="830bc-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="830bc-123">這些測試會判斷您的邊緣伺服器是否為：</span><span class="sxs-lookup"><span data-stu-id="830bc-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="830bc-124">從您的網路外部使用 telnet 用戶端來偵聽必要的埠。</span><span class="sxs-lookup"><span data-stu-id="830bc-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="830bc-125">例如： telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="830bc-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="830bc-126">您應該針對您在 Edge 伺服器或 Edge 伺服器池中所使用的埠執行上述測試，視您的部署而定。</span><span class="sxs-lookup"><span data-stu-id="830bc-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="830bc-127">執行正確的外部 DNS 解析。</span><span class="sxs-lookup"><span data-stu-id="830bc-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="830bc-128">從您的網路外部，ping Edge 伺服器或 Edge 伺服器池中的每個外部 Fqdn。</span><span class="sxs-lookup"><span data-stu-id="830bc-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="830bc-129">即使 ping 失敗，您也會看到 IP 位址，您可以將您之前指派的 IP 位址進行比較。</span><span class="sxs-lookup"><span data-stu-id="830bc-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

