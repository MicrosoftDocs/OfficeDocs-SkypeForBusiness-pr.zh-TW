---
title: Lync Server 2013： 移除已驗證的使用者權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd54da7201889e9ca2ab8d2c40a84ad082fa1686
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="b3add-102">Lync Server 2013 中移除已驗證的使用者權限</span><span class="sxs-lookup"><span data-stu-id="b3add-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3add-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="b3add-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b3add-104">在鎖定的 Active Directory 環境中，會從預設 Active Directory 容器 (包括「使用者」、「設定」或「系統」，以及儲存「使用者」和「電腦」物件的組織單位 (OU)) 中移除已驗證的使用者存取控制項目 (ACE)。</span><span class="sxs-lookup"><span data-stu-id="b3add-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="b3add-105">移除已驗證的使用者 ACE，可防止對 Active Directory 資訊進行讀取存取。</span><span class="sxs-lookup"><span data-stu-id="b3add-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="b3add-106">不過，移除 Ace 建立 Lync Server 2013 的問題因為若要允許使用者執行網域準備在這些容器的讀取權限而定。</span><span class="sxs-lookup"><span data-stu-id="b3add-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="b3add-p102">在此情況下，Domain Admins 群組的成員資格 (執行網域準備、伺服器啟動及集區建立所需的成員資格) 就不會再授與預設容器中所儲存 Active Directory 資訊的讀取存取權。您必須手動授與樹系根網域中各種容器的讀取存取權限，才能檢查必要的樹系準備程序是否完成。</span><span class="sxs-lookup"><span data-stu-id="b3add-p102">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers. You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="b3add-109">若要啟用使用者，以便在任何非樹系根網域上執行網域準備、伺服器啟動或集區建立作業，您有以下的選項：</span><span class="sxs-lookup"><span data-stu-id="b3add-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="b3add-110">使用屬於 Enterprise Admins 群組，以執行網域準備作業的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b3add-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="b3add-111">使用為 Domain Admins 群組成員的帳戶，並將樹系根網域中下列每個容器的讀取存取權限授與此帳戶：</span><span class="sxs-lookup"><span data-stu-id="b3add-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="b3add-112">網域</span><span class="sxs-lookup"><span data-stu-id="b3add-112">Domain</span></span>
    
      - <span data-ttu-id="b3add-113">設定或系統</span><span class="sxs-lookup"><span data-stu-id="b3add-113">Configuration or System</span></span>

<span data-ttu-id="b3add-114">如果您不想要使用屬於 Enterprise Admins 群組成員的帳戶來執行網域準備或其他設定工作，請將樹系根中相關容器的讀取存取權明確授與想要使用的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b3add-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="b3add-115">將樹系根網域中容器的讀取存取權限授與使用者</span><span class="sxs-lookup"><span data-stu-id="b3add-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="b3add-116">使用屬於樹系根網域之 Domain Admins 群組成員的帳戶，登入已加入樹系根網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="b3add-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="b3add-117">為樹系根網域執行 adsiedit.msc。</span><span class="sxs-lookup"><span data-stu-id="b3add-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="b3add-118">如果已從「網域」、「設定」或「系統」容器中移除已驗證的使用者 ACE，則必須授與容器的唯讀權限 (如下列各步驟所述)。</span><span class="sxs-lookup"><span data-stu-id="b3add-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="b3add-119">用滑鼠右鍵按一下容器，然後按一下 **[內容]**。</span><span class="sxs-lookup"><span data-stu-id="b3add-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="b3add-120">按一下 **[安全性]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b3add-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="b3add-121">按一下 [進階]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b3add-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="b3add-122">在 [使用權限]\*\*\*\* 索引標籤上，按一下 [新增]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b3add-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="b3add-123">輸入的使用者或群組使用下列格式來接收權限名稱： `domain\account name`，然後按一下 [**確定]**。</span><span class="sxs-lookup"><span data-stu-id="b3add-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="b3add-124">在 **[物件]** 索引標籤的 **[套用到]** 中，按一下 **[只有此物件]**。</span><span class="sxs-lookup"><span data-stu-id="b3add-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="b3add-125">在 **[使用權限]** 中，按一下 **[允許]** 欄以選取下列「允許 ACE」：**[清單內容]**、**[讀取全部內容]** 和 **[讀取權限]**。</span><span class="sxs-lookup"><span data-stu-id="b3add-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="b3add-126">按兩次 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b3add-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="b3add-127">針對步驟 2 中列出的任何相關容器，重複執行上述步驟。</span><span class="sxs-lookup"><span data-stu-id="b3add-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

