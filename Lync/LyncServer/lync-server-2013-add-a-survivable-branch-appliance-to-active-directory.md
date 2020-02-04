---
title: Lync Server 2013：將 Survivable Branch Appliance 新增到 Active Directory
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
ms.openlocfilehash: 8712dcb5b68522a8b770aac63c5a37a1a70a669a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-survivable-branch-appliance-to-active-directory-in-lync-server-2013"></a><span data-ttu-id="bfec8-102">在 Lync Server 2013 中將 Survivable Branch Appliance 新增到 Active Directory</span><span class="sxs-lookup"><span data-stu-id="bfec8-102">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfec8-103">_**主題上次修改日期：** 2012-09-23_</span><span class="sxs-lookup"><span data-stu-id="bfec8-103">_**Topic Last Modified:** 2012-09-23_</span></span>

<span data-ttu-id="bfec8-104">如果您打算部署 Survivable 分支裝置，您必須將 Survivable 分支裝置新增至 Active Directory 網域服務。</span><span class="sxs-lookup"><span data-stu-id="bfec8-104">If you plan to deploy a Survivable Branch Appliance, you must add the Survivable Branch Appliance to Active Directory Domain Services.</span></span> <span data-ttu-id="bfec8-105">在中央網站執行此程式。</span><span class="sxs-lookup"><span data-stu-id="bfec8-105">Perform this procedure at the central site.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bfec8-106">只有在部署 Survivable 分支裝置時，才會執行此程式。</span><span class="sxs-lookup"><span data-stu-id="bfec8-106">Perform this procedure only if you are deploying a Survivable Branch Appliance.</span></span> <span data-ttu-id="bfec8-107">如果您要部署 Survivable 分支伺服器，請勿執行此動作。</span><span class="sxs-lookup"><span data-stu-id="bfec8-107">Do not perform it if you are deploying a Survivable Branch Server.</span></span>



</div>

<div>

## <a name="to-add-an-survivable-branch-appliance-to-active-directory-domain-services"></a><span data-ttu-id="bfec8-108">將 Survivable 分支裝置新增至 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="bfec8-108">To add an Survivable Branch Appliance to Active Directory Domain Services</span></span>

1.  <span data-ttu-id="bfec8-109">以企業系統管理員群組的成員身分登入成員伺服器。</span><span class="sxs-lookup"><span data-stu-id="bfec8-109">Log on to a member server as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="bfec8-110">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **Active Directory 使用者和電腦**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-110">Click **Start**, click **Administrative Tools**, and then click **Active Directory Users and Computers**.</span></span>

3.  <span data-ttu-id="bfec8-111">在 [**動作**] 功能表上，按一下 [**新增**]，然後按一下 [**電腦**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-111">On the **Actions** menu, click **New** and then click **Computer**.</span></span>

4.  <span data-ttu-id="bfec8-112">在 [**新物件-電腦**] 對話方塊中，輸入 Survivable 分支裝置電腦物件的名稱（例如，BranchOffice1），然後按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-112">In the **New Object-Computer** dialog box, type in a name for the Survivable Branch Appliance computer object (for example, BranchOffice1), and then click **Change**.</span></span>

5.  <span data-ttu-id="bfec8-113">在 [**選取使用者或群組**] 對話方塊中，新增 [RTCUniversalSBATechnicians] 群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfec8-113">In the **Select User or Group** dialog box, add the RTCUniversalSBATechnicians group and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bfec8-114">分支網站上的 [RTCUniversalSBATechnicians] 群組成員稍後會將此裝置新增至網域。</span><span class="sxs-lookup"><span data-stu-id="bfec8-114">A member of the RTCUniversalSBATechnicians group at the branch site will add this device to the domain later.</span></span>

    
    </div>

6.  <span data-ttu-id="bfec8-115">按一下 **[確定]** 以儲存 Survivable 分支裝置電腦物件。</span><span class="sxs-lookup"><span data-stu-id="bfec8-115">Click **OK** to save the Survivable Branch Appliance computer object.</span></span>

7.  <span data-ttu-id="bfec8-116">按一下 [**開始**]，按一下 [**管理工具**]，然後按一下 [ **ADSI 編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-116">Click **Start**, click **Administrative Tools**, and then click **ADSI Edit**.</span></span>

8.  <span data-ttu-id="bfec8-117">在 [ **ADSI 編輯**] 中，以滑鼠右鍵按一下您在先前步驟中建立的電腦物件，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-117">In **ADSI Edit**, right-click the computer object that you created in the previous steps, and then click **Properties**.</span></span>

9.  <span data-ttu-id="bfec8-118">在屬性清單中，按一下 [ **servicePrincipalName**]，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-118">In the attribute list, click **servicePrincipalName**, and then click **Edit**.</span></span>

10. <span data-ttu-id="bfec8-119">在 [**要新增的值**] 欄位中，\<輸入 HOST\> / \<SBA Fqdn\> ，其中 SBA FQDN 是您 Survivable 分支裝置的完整功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="bfec8-119">In the **Value to add** field, type HOST/\<SBA FQDN\> where \<SBA FQDN\> is the fully qualified domain name (FQDN) of your Survivable Branch Appliance.</span></span> <span data-ttu-id="bfec8-120">例如，輸入**HOST/BranchOffice1**。</span><span class="sxs-lookup"><span data-stu-id="bfec8-120">For example, type **HOST/BranchOffice1.contoso.com**.</span></span>

11. <span data-ttu-id="bfec8-121">按一下 **[確定]** 儲存**servicePrincipalName**屬性設定，然後按一下 **[確定]** 儲存電腦物件的屬性。</span><span class="sxs-lookup"><span data-stu-id="bfec8-121">Click **OK** to save the **servicePrincipalName** attribute setting, and then click **OK** to save the computer object properties.</span></span>

12. <span data-ttu-id="bfec8-122">在**Active Directory 使用者和電腦**中，以滑鼠右鍵按一下 [**使用者**]，按一下 [**新增**]，然後按一下 [**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-122">In **Active Directory Users and Computers**, right-click **Users**, click **New**, and then click **User**.</span></span>

13. <span data-ttu-id="bfec8-123">在嚮導中輸入資訊，為 Survivable 分支裝置技術人員建立網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="bfec8-123">Enter information into the wizard to create a domain user account for a Survivable Branch Appliance technician.</span></span>

14. <span data-ttu-id="bfec8-124">在**Active Directory 使用者和電腦**中，按一下 [**使用者**]，以滑鼠右鍵按一下使用者物件，然後按一下 [**新增至群組**]。</span><span class="sxs-lookup"><span data-stu-id="bfec8-124">In **Active Directory Users and Computers**, click **Users**, right-click the user object, and then click **Add to a group**.</span></span>

15. <span data-ttu-id="bfec8-125">在 **[輸入要選取的物件名稱**] 中，輸入**RTCUniversalSBATechnicians**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bfec8-125">In **Enter the object names to select**, type **RTCUniversalSBATechnicians**, and then click **OK**.</span></span>

16. <span data-ttu-id="bfec8-126">針對每個分支網站技術人員，重複執行步驟12-15。</span><span class="sxs-lookup"><span data-stu-id="bfec8-126">Repeat Steps 12-15 for each branch site technician.</span></span>

<span data-ttu-id="bfec8-127">**後續步驟**：[在 Lync Server 2013 中新增分支網站至您的拓撲](lync-server-2013-add-branch-sites-to-your-topology.md)</span><span class="sxs-lookup"><span data-stu-id="bfec8-127">**Next step**: [Add branch sites to your topology in Lync Server 2013](lync-server-2013-add-branch-sites-to-your-topology.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

