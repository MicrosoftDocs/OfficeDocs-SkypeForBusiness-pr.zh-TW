---
title: 指派會議原則以支援匿名使用者
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 您可以將會議原則設定為支援匿名使用者, 並將該會議原則套用到特定使用者, 以控制誰能邀請匿名使用者。
ms.openlocfilehash: d7956e68db3330f0804e6161e0eeaf52958bc588
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188899"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="8b2fb-103">指派會議原則以支援商務用 Skype Server 中的匿名使用者</span><span class="sxs-lookup"><span data-stu-id="8b2fb-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="8b2fb-104">根據預設, 所有使用者都會被禁止邀請匿名使用者參與會議。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="8b2fb-105">您可以將會議原則設定為支援匿名使用者, 並將該會議原則套用到特定使用者, 以控制誰能邀請匿名使用者。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="8b2fb-106">如需有關如何設定會議原則以支援匿名使用者的詳細資料, 請參閱[在商務用 Skype server 中建立會議原則](../../conferencing/create-policies.md)以及[管理聯盟及外部存取權至商務用 skype 伺服器](../managing-federation-and-external-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="8b2fb-107">使用本節中的程式, 將您已建立的會議原則套用至一或多個使用者或使用者群組。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="8b2fb-108">除了設定及套用原則以讓使用者邀請匿名使用者, 您也必須為貴組織啟用匿名使用者支援。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="8b2fb-109">如需詳細資訊, 請參閱[在商務用 Skype Server 中設定控制公用使用者存取權的原則](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="8b2fb-110">設定匿名參與會議的使用者原則</span><span class="sxs-lookup"><span data-stu-id="8b2fb-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="8b2fb-111">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或是擁有同等的使用者權利), 或是指派給 CsAdministrator 角色, 登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8b2fb-112">開啟瀏覽器視窗, 然後輸入系統管理員 URL, 開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8b2fb-113">在左側導覽列中, 按一下 [**會議**], 然後執行下列其中一項操作:</span><span class="sxs-lookup"><span data-stu-id="8b2fb-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="8b2fb-114">若要建立新的使用者原則, 請按一下 [**新增**], 然後按一下 [**使用者原則**]。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="8b2fb-115">在 [Name] (**名稱**) 欄位中建立唯一的名稱, 以指出使用者原則所涵蓋的內容 (例如, 允許與匿名使用者進行通訊的使用者原則**EnableAnonymous** )。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="8b2fb-116">若要設定現有的使用者原則, 請按一下表格中所列的適當原則, 按一下 [**編輯**], 然後按一下 [**顯示詳細資料**]。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="8b2fb-117">在 [**會議原則**] 對話方塊中, 選取 [**允許參與者邀請匿名使用者**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="8b2fb-118">按一下 [認可]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="8b2fb-119">在左側導覽列中, 按一下 [**使用者**], 搜尋您要設定的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="8b2fb-120">在列出搜尋結果的表格中，依序按一下使用者帳戶、[編輯]\*\*\*\* 及 [顯示詳細資料]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="8b2fb-121">在 [**會議原則**] 下的 [**編輯商務用 Skype Server 使用者**] 中, 選取您想要套用至此使用者的 [匿名使用者存取設定] 使用者原則。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="8b2fb-122">[ <STRONG> &lt;自動&gt; </STRONG>設定] 會套用預設伺服器安裝設定, 且由伺服器自動套用。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="8b2fb-123">若要讓使用者邀請匿名使用者加入會議, 您也必須在組織中啟用匿名使用者支援。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="8b2fb-124">如需詳細資訊, 請參閱[在商務用 Skype Server 中設定控制公用使用者存取權的原則](../external-access-policies/configure-policies-to-control-public-user-access.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2fb-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

