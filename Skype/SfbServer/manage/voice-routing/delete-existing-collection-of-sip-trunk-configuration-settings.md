---
title: 刪除商務用 Skype Server 中現有的 SIP 幹線設定集合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 exchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。 '
ms.openlocfilehash: 55636cc34df4b05ccdd4b9035ef3aa4bb169e9a0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187024"
---
# <a name="delete-an-existing-collection-of-sip-trunk-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="3e738-103">刪除商務用 Skype Server 中現有的 SIP 幹線設定集合</span><span class="sxs-lookup"><span data-stu-id="3e738-103">Delete an existing collection of SIP trunk configuration settings in Skype for Business Server</span></span>

<span data-ttu-id="3e738-104">SIP 幹線設定設定會定義在服務提供者上, exchange 中繼伺服器與公用交換式電話網絡 (PSTN) 閘道、IP 公用分支 exchange (PBX) 或會話邊界控制器 (SBC) 之間的關聯性與能力。</span><span class="sxs-lookup"><span data-stu-id="3e738-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="3e738-105">這些設定會以指定的方式執行以下操作:</span><span class="sxs-lookup"><span data-stu-id="3e738-105">These settings do such things as specify:</span></span>

- <span data-ttu-id="3e738-106">是否應該在 trunks 上啟用媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="3e738-106">Whether media bypass should be enabled on the trunks.</span></span>
- <span data-ttu-id="3e738-107">傳送即時傳輸控制通訊協定 (RTCP) 資料包的條件。</span><span class="sxs-lookup"><span data-stu-id="3e738-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>
- <span data-ttu-id="3e738-108">每個幹線是否都需要安全的即時通訊協定 (SRTP) 加密。</span><span class="sxs-lookup"><span data-stu-id="3e738-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="3e738-109">當您安裝商務用 Skype Server 時, 系統會為您建立一個全域 SIP 中繼設定。</span><span class="sxs-lookup"><span data-stu-id="3e738-109">When you install Skype for Business Server, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="3e738-110">這個全域設定集合無法刪除。</span><span class="sxs-lookup"><span data-stu-id="3e738-110">This global collection of settings cannot be deleted.</span></span> <span data-ttu-id="3e738-111">不過, 您可以使用商務用 Skype ServerControl 面板或[new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) Cmdlet, 將全域集合中的屬性「重設」為預設值。</span><span class="sxs-lookup"><span data-stu-id="3e738-111">However, you can use the Skype for Business ServerControl Panel or the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet to "reset" the properties in the global collection to their default values.</span></span> <span data-ttu-id="3e738-112">例如, 如果您已將 Enable3pccRefer 屬性設為 True, 當您重設全域集合時, Enable3pccRefer 屬性將會還原為預設值 False。</span><span class="sxs-lookup"><span data-stu-id="3e738-112">For example, if you have set the Enable3pccRefer property to True, when you reset the global collection the Enable3pccRefer property will revert to its default value of False.</span></span>

<span data-ttu-id="3e738-113">系統管理員也可以在網站範圍或服務範圍 (針對個別 PSTN 閘道) 建立自訂主幹設定設定。您可以移除這些自訂設定。</span><span class="sxs-lookup"><span data-stu-id="3e738-113">Administrators can also create custom trunk configuration settings at the site scope or at the service scope (for an individual PSTN gateway); these custom settings can be removed.</span></span> <span data-ttu-id="3e738-114">移除這些自訂設定時, 請記住下列事項:</span><span class="sxs-lookup"><span data-stu-id="3e738-114">When removing these custom settings keep the following in mind:</span></span>

- <span data-ttu-id="3e738-115">如果您移除服務範圍設定, 這些設定所管理的 SIP 幹線將由套用至其網站的設定來管理 (如果存在的話)。</span><span class="sxs-lookup"><span data-stu-id="3e738-115">If you remove service scope settings, then the SIP trunk managed by those settings will be managed by the settings applied to their site, if they exist.</span></span> <span data-ttu-id="3e738-116">如果網站設定不存在, 這些 trunks 就會受到中繼設定設定的全域集合的管理。</span><span class="sxs-lookup"><span data-stu-id="3e738-116">If site settings do not exist, those trunks will then be managed by the global collection of trunk configuration settings.</span></span>
- <span data-ttu-id="3e738-117">如果您移除網站範圍的設定, 由這些設定所管理的任何 SIP trunks 現在都將由「中繼設定」全域集合來管理。</span><span class="sxs-lookup"><span data-stu-id="3e738-117">If you remove site-scoped settings then any SIP trunks managed by those settings will now be managed by the global collection of trunk configuration settings.</span></span>

<span data-ttu-id="3e738-118">**若要在商務用 Skype Server 控制台中移除主幹設定設定**</span><span class="sxs-lookup"><span data-stu-id="3e738-118">**To remove trunk configuration settings with the Skype for Business Server Control Panel**</span></span> 

1. <span data-ttu-id="3e738-119">在商務用 Skype Server [控制台] 中, 按一下 [**語音路由**], 然後按一下 [**幹線**設定]。</span><span class="sxs-lookup"><span data-stu-id="3e738-119">In the Skype for Business Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>
2. <span data-ttu-id="3e738-120">在 [**幹線**設定] 索引標籤上, 選取要刪除的 SIP 中繼設定集合, 按一下 [**編輯**], 然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="3e738-120">On the **Trunk Configuration** tab, select the collection of SIP trunk configuration settings to be deleted, click **Edit**, and then click **Delete**.</span></span> <span data-ttu-id="3e738-121">若要在相同的作業中刪除多個集合, 請按一下要刪除的第一個集合, 然後按住 Ctrl 鍵並按一下您想要移除的任何其他集合。</span><span class="sxs-lookup"><span data-stu-id="3e738-121">To delete multiple collections in the same operation, click the first collection to be deleted, then hold down the Ctrl key and click any additional collections that you want to remove.</span></span>
3. <span data-ttu-id="3e738-122">集合的**State**屬性會更新為**未提交**。</span><span class="sxs-lookup"><span data-stu-id="3e738-122">The **State** property for the collection will be updated to **Uncommitted**.</span></span> <span data-ttu-id="3e738-123">若要確認變更, 並刪除收藏, 請按一下 [**認可**], 然後按一下 [**全部確認**]。</span><span class="sxs-lookup"><span data-stu-id="3e738-123">To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>
4. <span data-ttu-id="3e738-124">在 [**未提交的語音設定**] 對話方塊中, 按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3e738-124">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>
5. <span data-ttu-id="3e738-125">在**商務用 Skype Server [控制台**] 對話方塊中, 按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3e738-125">In the **Skype for Business Server Control Panel** dialog box, click **OK**.</span></span>
6. <span data-ttu-id="3e738-126">如果您改變主意, 並決定不刪除收藏, 請按一下 [**認可**], 然後按一下 [**取消所有未提交的變更**]。</span><span class="sxs-lookup"><span data-stu-id="3e738-126">If you change your mind and decide not to delete the collection, click **Commit**, and then click **Cancel All Uncommitted Changes**.</span></span> <span data-ttu-id="3e738-127">當**商務用 Skype Server [控制台**] 對話方塊出現時, 請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="3e738-127">When the **Skype for Business Server Control Panel** dialog box appears, click **OK**.</span></span>

## <a name="removing-trunk-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3e738-128">使用 Windows PowerShell Cmdlet 移除主幹設定設定</span><span class="sxs-lookup"><span data-stu-id="3e738-128">Removing trunk configuration settings by using Windows PowerShell cmdlets</span></span>


<span data-ttu-id="3e738-129">您可以使用 Windows PowerShell 與**Remove new-cstrunkconfiguration** Cmdlet 來刪除主幹設定設定。</span><span class="sxs-lookup"><span data-stu-id="3e738-129">You can delete trunk configuration settings by using Windows PowerShell and the **Remove-CsTrunkConfiguration** cmdlet.</span></span> <span data-ttu-id="3e738-130">您可以從商務用 Skype Server Management 命令介面或從 Windows PowerShell 遠端會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="3e738-130">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

<span data-ttu-id="3e738-131">**移除指定的設定集合**</span><span class="sxs-lookup"><span data-stu-id="3e738-131">**To remove a specified collection of settings**</span></span>

<span data-ttu-id="3e738-132">下列命令會移除套用至雷德蒙網站的幹線設定設定:</span><span class="sxs-lookup"><span data-stu-id="3e738-132">The following command removes the trunk configuration settings applied to the Redmond site:</span></span>

`Remove-CsTrunkConfiguration -Identity site:Redmond`

<span data-ttu-id="3e738-133">**若要移除所有套用至網站範圍的集合**</span><span class="sxs-lookup"><span data-stu-id="3e738-133">**To remove all the collections applied to the site scope**</span></span>

<span data-ttu-id="3e738-134">這個命令會移除所有已套用至服務範圍的中繼設定設定:</span><span class="sxs-lookup"><span data-stu-id="3e738-134">This command removes all the trunk configuration settings applied to the service scope:</span></span>

`Get-CsTrunkConfiguration -Filter "service:*" | Remove-CsTrunkConfiguration`

<span data-ttu-id="3e738-135">**若要移除已啟用媒體旁路的所有集合**</span><span class="sxs-lookup"><span data-stu-id="3e738-135">**To remove all the collections where media bypass is enabled**</span></span>

<span data-ttu-id="3e738-136">下列命令會移除已啟用媒體略過的所有主幹設定設定:</span><span class="sxs-lookup"><span data-stu-id="3e738-136">The following command removes all the trunk configuration settings where media bypass has been enabled:</span></span>

`Get-CsTrunkConfiguration | Where-Object {$_.EnableBypass -eq $True} | Remove-CsTrunkConfiguration`

<span data-ttu-id="3e738-137">如需詳細資訊, 請參閱[Remove new-cstrunkconfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) Cmdlet 的說明主題。</span><span class="sxs-lookup"><span data-stu-id="3e738-137">For more information, see the help topic for the [Remove-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsTrunkConfiguration) cmdlet.</span></span>
