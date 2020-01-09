---
title: Lync Server 2013：準備網域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cd8c09346c8f5b562a72e77b9ba40915b480c91
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="e2ef0-102">針對 Lync Server 2013 準備網域</span><span class="sxs-lookup"><span data-stu-id="e2ef0-102">Preparing domains for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2ef0-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e2ef0-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e2ef0-104">[網域準備] 是為 Lync Server 2013 準備 Active Directory 網域服務的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="e2ef0-105">[網域準備] 步驟會將必要的存取控制專案（Ace）新增至通用群組，以便在網域中授與主機及管理使用者的許可權。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="e2ef0-106">[網域準備] 會在網域根目錄和三個內建容器中建立 Ace：使用者、電腦及網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="e2ef0-107">您可以在要部署 Lync Server 的網域中的任何電腦上執行網域準備。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="e2ef0-108">您必須準備將主持 Lync Server 或使用者的每個網域。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="e2ef0-109">如果已停用許可權繼承，或在您的組織中停用驗證的使用者許可權，您必須在網域準備期間執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="e2ef0-110">如需詳細資訊，請參閱[在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="e2ef0-111">如果您的組織使用組織單位（OU），而不是三個內建的容器（也就是使用者、電腦及網網域控制站），則您必須授與已驗證使用者群組的 Ou 讀取權限。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="e2ef0-112">網域準備必須具備容器的讀取權。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="e2ef0-113">如果 [經過驗證的使用者] 群組沒有 OU 的讀取存取權，請執行**CsOuPermission** Cmdlet，如下列程式碼範例所示，以授與每個 OU 的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="e2ef0-114">如需**授權 CsOuPermission** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="e2ef0-115">如需在網域根目錄和 [使用者]、[電腦] 和 [網網域控制站] 容器中建立之 Ace 的詳細資料，請參閱<A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的 [由網域準備所做的變更</A>]。</span><span class="sxs-lookup"><span data-stu-id="e2ef0-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e2ef0-116">本節內容</span><span class="sxs-lookup"><span data-stu-id="e2ef0-116">In This Section</span></span>

  - [<span data-ttu-id="e2ef0-117">為 Lync Server 2013 執行網域準備</span><span class="sxs-lookup"><span data-stu-id="e2ef0-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="e2ef0-118">將 Cmdlet 用於 Lync Server 2013 的反向網域準備</span><span class="sxs-lookup"><span data-stu-id="e2ef0-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

