---
title: Lync Server 2013：準備網域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a37c365732785198e45a546f2352c51ccb42f9dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506940"
---
# <a name="preparing-domains-for-lync-server-2013"></a><span data-ttu-id="bb533-102">準備 Lync Server 2013 的網域</span><span class="sxs-lookup"><span data-stu-id="bb533-102">Preparing domains for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb533-103">_**主題上次修改日期：** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bb533-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bb533-104">網域準備是準備 Lync Server 2013 的 Active Directory 網域服務的最後一個步驟。</span><span class="sxs-lookup"><span data-stu-id="bb533-104">Domain preparation is the final step in preparing Active Directory Domain Services for Lync Server 2013.</span></span> <span data-ttu-id="bb533-105">網域準備步驟會將必要的存取控制項目 (ACE) 新增至萬用群組，而這些群組會授與權限來裝載和管理網域內的使用者。</span><span class="sxs-lookup"><span data-stu-id="bb533-105">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="bb533-106">網域準備作業會在網域根目錄和三個內建容器上建立 ACE：使用者、電腦和網域控制站。</span><span class="sxs-lookup"><span data-stu-id="bb533-106">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="bb533-107">您可以在要部署 Lync Server 的網域中的任何電腦上執行網域準備工作。</span><span class="sxs-lookup"><span data-stu-id="bb533-107">You can run domain preparation on any computer in the domain where you are deploying Lync Server.</span></span> <span data-ttu-id="bb533-108">您必須準備將主控 Lync Server 或使用者的每個網域。</span><span class="sxs-lookup"><span data-stu-id="bb533-108">You must prepare every domain that will host Lync Server or users.</span></span>

<span data-ttu-id="bb533-109">如果停用許可權繼承或已驗證使用者許可權已在您的組織中停用，您必須在準備網域期間執行其他步驟。</span><span class="sxs-lookup"><span data-stu-id="bb533-109">If permissions inheritance is disabled or authenticated user permissions are disabled in your organization, you must perform additional steps during domain preparation.</span></span> <span data-ttu-id="bb533-110">如需詳細資訊，請參閱 [在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="bb533-110">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).</span></span>

<span data-ttu-id="bb533-111">如果您的組織使用組織單位 (OU) 而不是三個內建容器 (也就是) 的使用者、電腦和網域控制站，您必須授與已驗證使用者群組之 Ou 的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="bb533-111">If your organization uses organizational units (OU) instead of the three built-in containers (that is, Users, Computers, and Domain Controllers), you must grant read access to the OUs for the Authenticated Users group.</span></span> <span data-ttu-id="bb533-112">執行網域準備工作時，必須要有容器的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="bb533-112">Read access to the containers is required for domain preparation.</span></span> <span data-ttu-id="bb533-113">如果 [已驗證使用者] 群組沒有 OU 的「讀取」存取權，請執行 **Grant-CsOuPermission** 指令程式，如下列程式碼範例所示，以授與每個 OU 的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="bb533-113">If the Authenticated Users group does not have read access to the OU, run the **Grant-CsOuPermission** cmdlet as illustrated in the following code examples to grant read permissions for each OU.</span></span>

   ```PowerShell
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```PowerShell
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

<span data-ttu-id="bb533-114">如需 **Grant-CsOuPermission** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="bb533-114">For details about the **Grant-CsOuPermission** cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div class="">


> [!TIP]  
> <span data-ttu-id="bb533-115">如需在網域根及使用者、電腦和網域控制站容器中建立之 Ace 的詳細資訊，請參閱 <A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的網域準備所做的變更</A>。</span><span class="sxs-lookup"><span data-stu-id="bb533-115">For details about the ACEs created on the domain root and in the Users, Computers, and Domain Controllers containers, see <A href="lync-server-2013-changes-made-by-domain-preparation.md">Changes made by domain preparation in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bb533-116">本章節內容</span><span class="sxs-lookup"><span data-stu-id="bb533-116">In This Section</span></span>

  - [<span data-ttu-id="bb533-117">對 Lync Server 2013 執行網域準備</span><span class="sxs-lookup"><span data-stu-id="bb533-117">Running domain preparation for Lync Server 2013</span></span>](lync-server-2013-running-domain-preparation.md)

  - [<span data-ttu-id="bb533-118">使用 Cmdlet 進行 Lync Server 2013 的反向網域準備</span><span class="sxs-lookup"><span data-stu-id="bb533-118">Using cmdlets to reverse domain preparation for Lync Server 2013</span></span>](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

