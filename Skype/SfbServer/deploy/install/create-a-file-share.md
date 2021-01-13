---
title: 在商務用 Skype Server 中建立檔案共用
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 摘要：瞭解如何在安裝商務用 Skype Server 的過程中建立 Windows Server 檔案共用。 從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812233"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="35771-104">在商務用 Skype Server 中建立檔案共用</span><span class="sxs-lookup"><span data-stu-id="35771-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="35771-105">**摘要：** 瞭解如何在安裝商務用 Skype Server 時，建立 Windows Server 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="35771-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="35771-106">從 Microsoft 評估中心下載免費試用版的商務用 Skype Server，網址如下： [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。</span><span class="sxs-lookup"><span data-stu-id="35771-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="35771-107">商務用 Skype 伺服器需要檔案共用，使整個拓撲中的電腦可以交換檔案。</span><span class="sxs-lookup"><span data-stu-id="35771-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="35771-108">建立檔案共用是商務用 Skype 伺服器安裝程式中的步驟2之8。</span><span class="sxs-lookup"><span data-stu-id="35771-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="35771-109">您可以依任何循序執行步驟1到5。</span><span class="sxs-lookup"><span data-stu-id="35771-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="35771-110">不過，您必須依序執行步驟6、7和8，並在圖表中所述的步驟1到5之後進行。</span><span class="sxs-lookup"><span data-stu-id="35771-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="35771-111">如需檔案共用的規劃詳細資料，請參閱商務用 skype server 2019 的 [商務用 Skype 伺服器](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 或 [伺服器需求](../../../SfBServer2019/plan/system-requirements.md)環境需求。</span><span class="sxs-lookup"><span data-stu-id="35771-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![一覽表圖表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="35771-113">建立基本檔案共用</span><span class="sxs-lookup"><span data-stu-id="35771-113">Create a basic file share</span></span>

<span data-ttu-id="35771-114">本節會逐步引導您建立基本的 Windows Server 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="35771-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="35771-115">商務用 Skype Server 支援基本 Windows Server 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="35771-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="35771-116">不過，它並未明確提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="35771-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="35771-117">在高可用性環境中，建議使用分散式檔案系統 (DFS) 檔案共用。</span><span class="sxs-lookup"><span data-stu-id="35771-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="35771-118">如需高可用性檔案共用及 DFS 的詳細資訊，請參閱 [在商務用 Skype Server 中規劃高可用性和嚴重損壞修復](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="35771-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="35771-119">Windows Server 2012 R2 已使用 Windows Server 平臺，在提供儲存區域網路 (SAN) 類似的檔案共用解決方案上進行了重大的大幅突破。</span><span class="sxs-lookup"><span data-stu-id="35771-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="35771-120">與傳統的 SAN 裝置相較時，Windows Server 2012 R2 儲存解決方案可以以極小的效能影響降低成本。</span><span class="sxs-lookup"><span data-stu-id="35771-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="35771-121">如需有關 Windows Server 2012 R2 中檔案共用選項的詳細資訊，請參閱可下載的白皮書 [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。</span><span class="sxs-lookup"><span data-stu-id="35771-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="35771-122">觀賞 **建立檔案共用** 的影片步驟：</span><span class="sxs-lookup"><span data-stu-id="35771-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="35771-123">建立基本檔案共用</span><span class="sxs-lookup"><span data-stu-id="35771-123">Create a basic file share</span></span>

1. <span data-ttu-id="35771-124">登入將主檔案共用的電腦。</span><span class="sxs-lookup"><span data-stu-id="35771-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="35771-125">以滑鼠右鍵按一下您要共用的資料夾，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="35771-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="35771-126">選取 [ **共用** ] 索引標籤，然後按一下 [ **高級共用**]。</span><span class="sxs-lookup"><span data-stu-id="35771-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="35771-127">按一下 [ **共用此資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="35771-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="35771-128">按一下 [權限]。</span><span class="sxs-lookup"><span data-stu-id="35771-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="35771-129">新增主控檔案共用之伺服器的本機系統 **管理員** 群組、授與 **允許：完全控制、變更和讀取** 許可權，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="35771-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="35771-130">再按一下 **[確定]** ，記下網路路徑。</span><span class="sxs-lookup"><span data-stu-id="35771-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="35771-131">按一下 [ **完成** ]，關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="35771-131">Click **Done** to close the wizard.</span></span>
    
     ![共用資料夾的 [共用] 索引標籤。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="35771-133">如果檔案存放區裝載于 DFS 共用上，則會收到下列警告：</span><span class="sxs-lookup"><span data-stu-id="35771-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="35771-134">警告：無法存取 "" 的共用許可權 \\ <domain> \<share> 。</span><span class="sxs-lookup"><span data-stu-id="35771-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="35771-135">如果您不是檔案伺服器上的系統管理員，或者這是分散式檔案系統 (DFS) 共用，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="35771-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="35771-136">如果已設定共用許可權，則可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="35771-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="35771-137">如果是新的共用，請參閱檔，以瞭解手動設定共用許可權的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="35771-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="35771-138">由於無法存取 DFS 共用上的共用許可權，商務用 Skype 伺服器將無法明確設定檔案共用上的群組。</span><span class="sxs-lookup"><span data-stu-id="35771-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="35771-139">若要確保商務用 Skype Server 元件可以存取具有適當許可權的檔案共用，請確定下列 RTC 群組新增具有「讀取」和「變更層級共用」許可權，除了具有「完全控制」共用許可權的本機管理員之外。</span><span class="sxs-lookup"><span data-stu-id="35771-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="35771-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35771-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="35771-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="35771-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="35771-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="35771-142">RTCUniversalServerAdmins</span></span>
