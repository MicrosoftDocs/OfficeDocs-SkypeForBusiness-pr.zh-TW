---
title: 刪除商務用 Skype Server 中現有的 SIP 幹線設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3b25f14d-884b-42dd-a866-460d276d3e43
description: 摘要：瞭解如何使用商務用 Skype Server 控制台刪除主幹設定設定的集合。
ms.openlocfilehash: 97a0820258a837968b88e6840232829f3ad11d21
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2020
ms.locfileid: "41000993"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b46fc-103">刪除商務用 Skype Server 中現有的 SIP 幹線設定集合</span><span class="sxs-lookup"><span data-stu-id="b46fc-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b46fc-104">**摘要：** 瞭解如何使用商務用 Skype Server [控制台] 刪除主幹設定的集合。</span><span class="sxs-lookup"><span data-stu-id="b46fc-104">**Summary:** Learn how to delete a collection of trunk configuration settings by using the Skype for Business Server Control Panel.</span></span>
  
<span data-ttu-id="b46fc-105">SIP 幹線設定設定會定義在服務提供者上，exchange 中繼伺服器與公用交換式電話網絡（PSTN）閘道、IP 公用分支 eXchange （PBX）或會話邊界控制器（SBC）之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="b46fc-105">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the Public Switched Telephone Network (PSTN) gateway, an IP-Public Branch eXchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="b46fc-106">這些設定會以指定的方式執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b46fc-106">These settings do such things as specify:</span></span>
  
- <span data-ttu-id="b46fc-107">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="b46fc-107">Whether media bypass should be enabled on the trunks.</span></span>
    
- <span data-ttu-id="b46fc-108">傳送即時傳輸控制通訊協定（RTCP）資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="b46fc-108">The conditions under which Realtime Transport Control Protocol (RTCP) packets are sent.</span></span>
    
- <span data-ttu-id="b46fc-109">每個幹線是否都需要安全的即時傳輸通訊協定（SRTP）加密。</span><span class="sxs-lookup"><span data-stu-id="b46fc-109">Whether or not Secure Realtime Transport Protocol (SRTP) encryption is required on each trunk.</span></span>
    
<span data-ttu-id="b46fc-110">當您安裝商務用 Skype Server 時，系統會為您建立一個全域 SIP 中繼設定。</span><span class="sxs-lookup"><span data-stu-id="b46fc-110">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="b46fc-111">這個全域設定集合無法刪除。</span><span class="sxs-lookup"><span data-stu-id="b46fc-111">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="b46fc-112">不過，您可以使用商務用 Skype Server 的 [控制台] 或 [ [new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) ] Cmdlet，將全域集合中的屬性 "reset" 成預設值。</span><span class="sxs-lookup"><span data-stu-id="b46fc-112">However, you can use the Skype for Business Server Control Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="b46fc-113">例如，如果您已將 Enable3pccRefer 屬性設為 True，當您重設全域集合時，Enable3pccRefer 屬性將會還原為預設值 False。</span><span class="sxs-lookup"><span data-stu-id="b46fc-113">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>
  
<span data-ttu-id="b46fc-114">系統管理員也可以在網站範圍或服務範圍（針對個別 PSTN 閘道）建立自訂主幹設定設定。您可以移除這些自訂設定。</span><span class="sxs-lookup"><span data-stu-id="b46fc-114">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="b46fc-115">移除這些自訂設定時，請記住下列事項：</span><span class="sxs-lookup"><span data-stu-id="b46fc-115">When removing these custom settings keep the following in mind:</span></span>
  
- <span data-ttu-id="b46fc-116">如果您移除服務範圍設定，這些設定所管理的 SIP 幹線將由套用至其網站的設定來管理（如果存在的話）。</span><span class="sxs-lookup"><span data-stu-id="b46fc-116">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="b46fc-117">如果網站設定不存在，這些 trunks 就會受到中繼設定設定的全域集合的管理。</span><span class="sxs-lookup"><span data-stu-id="b46fc-117">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
    
- <span data-ttu-id="b46fc-118">如果您移除網站範圍的設定，由這些設定所管理的任何 SIP trunks 現在都將由「中繼設定」全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="b46fc-118">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>
    
### <a name="to-remove-trunk-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="b46fc-119">若要在商務用 Skype Server 控制台中移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="b46fc-119">To remove trunk configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b46fc-120">在商務用 Skype Server 的 [控制台] 中，按一下 [**語音路由**]，然後按一下 [**幹線配置**]。</span><span class="sxs-lookup"><span data-stu-id="b46fc-120">In Skype for Business Server Control Panel, click **Voice Routing** and then click **Trunk Configuration**.</span></span>
    
2. <span data-ttu-id="b46fc-121">在 [**幹線**設定] 索引標籤上，選取要刪除的 SIP 中繼設定的集合，按一下 [**編輯**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="b46fc-121">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit** and then click **Delete**.</span></span> <span data-ttu-id="b46fc-122">若要在相同的作業中刪除多個集合，請按一下要刪除的第一個集合，然後按住 Ctrl 鍵並按一下您想要移除的任何其他集合。</span><span class="sxs-lookup"><span data-stu-id="b46fc-122">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
    
3. <span data-ttu-id="b46fc-123">集合的**State**屬性會更新為**未提交**。</span><span class="sxs-lookup"><span data-stu-id="b46fc-123">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="b46fc-124">若要確認變更，並刪除收藏，請按一下 [**認可**]，然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="b46fc-124">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
    
4. <span data-ttu-id="b46fc-125">在 [**未提交的語音設定**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b46fc-125">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
    
5. <span data-ttu-id="b46fc-126">在**商務用 Skype Server**的 [控制台] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b46fc-126">In the **Skype for Business Server Control Panel** dialog box click **OK**.</span></span>
    
6. <span data-ttu-id="b46fc-127">如果您改變主意，並決定不刪除收藏，請按一下 [**認可**]，然後按一下 [**取消所有未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="b46fc-127">If you change your mind and decide not to delete the collection, click **Commit** and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="b46fc-128">當**商務用 Skype Server [控制台**] 對話方塊出現時，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b46fc-128">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>
    
## <a name="removing-trunk-configuration-settings-by-using-skype-for-business-server-management-shell-cmdlets"></a><span data-ttu-id="b46fc-129">使用商務用 Skype Server Management Shell Cmdlet 移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="b46fc-129">Removing Trunk Configuration Settings by Using Skype for Business Server Management Shell Cmdlets</span></span>

<span data-ttu-id="b46fc-130">您可以使用商務用 Skype Server Management 命令介面和**new-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="b46fc-130">You can delete trunk configuration settings by using Skype for Business Server Management Shell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="b46fc-131">您可以從商務用 Skype Server Management 命令介面或從商務用 Skype Server Management Shell 的遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="b46fc-131">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Skype for Business Server Management Shell.</span></span>
  
### <a name="to-remove-a-specified-collection-of-settings"></a><span data-ttu-id="b46fc-132">移除指定的設定集合</span><span class="sxs-lookup"><span data-stu-id="b46fc-132">To remove a specified collection of settings</span></span>

- <span data-ttu-id="b46fc-133">下列命令會移除套用至雷德蒙網站的幹線設定設定：</span><span class="sxs-lookup"><span data-stu-id="b46fc-133">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>
    
  ```powershell
  Remove-CsTrunkConfiguration -Identity site:Redmond
  ```

### <a name="to-remove-all-the-collections-applied-to-the-site-scope"></a><span data-ttu-id="b46fc-134">若要移除所有套用至網站範圍的集合</span><span class="sxs-lookup"><span data-stu-id="b46fc-134">To remove all the collections applied to the site scope</span></span>

- <span data-ttu-id="b46fc-135">這個命令會移除所有已套用至服務範圍的中繼設定設定：</span><span class="sxs-lookup"><span data-stu-id="b46fc-135">This command removes all the trunk configuration settings applied to the service scope:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration
  ```

### <a name="to-remove-all-the-collections-where-media-bypass-is-enabled"></a><span data-ttu-id="b46fc-136">若要移除已啟用媒體旁路的所有集合</span><span class="sxs-lookup"><span data-stu-id="b46fc-136">To remove all the collections where media bypass is enabled</span></span>

- <span data-ttu-id="b46fc-137">下列命令會移除已啟用媒體略過的所有主幹設定設定：</span><span class="sxs-lookup"><span data-stu-id="b46fc-137">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>
    
  ```powershell
  Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration
  ```

<span data-ttu-id="b46fc-138">如需詳細資訊，請參閱[Remove new-cstrunkconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="b46fc-138">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cstrunkconfiguration?view=skype-ps) cmdlet.</span></span>
  

