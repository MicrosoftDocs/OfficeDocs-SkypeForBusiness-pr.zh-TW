---
title: Lync Server 2013： 新增至 Active Directory Survivable Branch Appliance
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a Survivable Branch Appliance to Active Directory
ms:assetid: 3e63507c-d60b-40ec-8bbe-586b1d707c3e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425906(v=OCS.15)
ms:contentKeyID: 48183938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da38ead0e1d27ef1024d8aac2ea030d2815e6cad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="c8f14-102">將 Survivable Branch Appliance 新增至 Lync Server 2013 中的 Active Directory</span><span class="sxs-lookup"><span data-stu-id="c8f14-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c8f14-103">_**主題上次修改日期：** 2012年-09-23_</span><span class="sxs-lookup"><span data-stu-id="c8f14-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="c8f14-104">如果您計劃要部署 Survivable Branch Appliance，您必須將 Survivable Branch Appliance 新增至 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="c8f14-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="c8f14-105">請在中央網站執行這項程序。</span><span class="sxs-lookup"><span data-stu-id="c8f14-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c8f14-106">只有當您要部署 Survivable Branch Appliance，請執行此程序。</span><span class="sxs-lookup"><span data-stu-id="c8f14-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="c8f14-107">請勿執行它如果您要部署 Survivable Branch 伺服器。</span><span class="sxs-lookup"><span data-stu-id="c8f14-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="c8f14-108">若要將 Survivable Branch Appliance 新增至 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="c8f14-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="c8f14-109">以 Enterprise Admins 群組成員的身分，登入成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="c8f14-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="c8f14-110">依序按一下 **[開始]**、**[系統管理工具]** 和 **[Active Directory 使用者和電腦]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="c8f14-111">在 **[執行]** 功能表上，依序按一下 **[新增]** 和 **[電腦]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="c8f14-112">在 [**新增物件-電腦**] 對話方塊中，輸入 Survivable Branch Appliance 的電腦物件 (例如 BranchOffice1) 的名稱，然後按一下 [**變更]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="c8f14-113">在 **[選取使用者或群組]** 對話方塊中，新增 RTCUniversalSBATechnicians 群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c8f14-114">稍後會由分支網站的 RTCUniversalSBATechnicians 群組成員將此裝置新增至網域。</span><span class="sxs-lookup"><span data-stu-id="c8f14-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="c8f14-115">按一下 **[確定]** 儲存 Survivable Branch Appliance 的電腦物件。</span><span class="sxs-lookup"><span data-stu-id="c8f14-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="c8f14-116">依序按一下 **[開始]**、**[系統管理工具]** 和 **[ADSI 編輯器]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="c8f14-117">在 **[ADSI 編輯器]** 中，用滑鼠右鍵按一下您於先前步驟建立的電腦物件，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="c8f14-118">在屬性清單中，依序按一下 **[servicePrincipalName]** 和 **[編輯]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="c8f14-119">**若要新增的值**] 欄位中輸入主機 /\<SBA FQDN\>其中\<SBA FQDN\>是您 Survivable Branch Appliance 的完整的網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c8f14-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="c8f14-120">例如，輸入 **HOST/BranchOffice1.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="c8f14-121">按一下 **[確定]** 儲存 **servicePrincipalName** 屬性設定，然後按一下 **[確定]** 儲存電腦物件內容。</span><span class="sxs-lookup"><span data-stu-id="c8f14-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="c8f14-122">在 **[Active Directory 使用者和電腦]** 中，用滑鼠右鍵按一下 **[使用者]**、按一下 **[新增]**，然後按一下 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="c8f14-123">若要為 Survivable Branch Appliance 技術人員建立網域使用者帳戶精靈中輸入資訊。</span><span class="sxs-lookup"><span data-stu-id="c8f14-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="c8f14-124">在 **[Active Directory 使用者和電腦]** 中，按一下 **[使用者]**、用滑鼠右鍵按一下使用者物件，然後按一下 **[加入群組中]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="c8f14-125">在 **[輸入物件名稱來選取]** 中，輸入 **RTCUniversalSBATechnicians**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c8f14-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="c8f14-126">針對每個分支網站技術人員，重複步驟 12-15。</span><span class="sxs-lookup"><span data-stu-id="c8f14-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="c8f14-127">**下一步**：[將分支網站新增至您在 Lync Server 2013 中的拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="c8f14-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

