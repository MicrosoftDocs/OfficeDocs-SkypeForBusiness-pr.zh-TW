---
title: Lync Server 2013：已移除已驗證使用者權限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Authenticated user permissions are removed
ms:assetid: 5fcd70a5-813a-4076-9bb6-5b0d47505038
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398425(v=OCS.15)
ms:contentKeyID: 48184304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d5e14b8129f771093ed9facb09d047ac7c36d32
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40973991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authenticated-user-permissions-are-removed-in-lync-server-2013"></a><span data-ttu-id="c1125-102">Lync Server 2013 中已移除已驗證使用者權限</span><span class="sxs-lookup"><span data-stu-id="c1125-102">Authenticated user permissions are removed in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1125-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c1125-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c1125-104">在鎖定的 Active Directory 環境中，已從預設 Active Directory 容器中移除經過驗證的使用者存取控制專案（Ace），包括使用者、配置或系統，以及使用者和電腦的組織單位（Ou）。儲存物件。</span><span class="sxs-lookup"><span data-stu-id="c1125-104">In a locked-down Active Directory environment, authenticated user access control entries (ACEs) are removed from the default Active Directory containers, including the Users, Configuration or System, and organizational units (OUs) where User and Computer objects are stored.</span></span> <span data-ttu-id="c1125-105">移除經過驗證的使用者 Ace 可防止讀取 Active Directory 資訊的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="c1125-105">Removing authenticated user ACEs prevents read access to Active Directory information.</span></span> <span data-ttu-id="c1125-106">不過，移除 Ace 會針對 Lync Server 2013 產生問題，因為它依賴于這些容器的讀取權限，以允許使用者執行網域準備。</span><span class="sxs-lookup"><span data-stu-id="c1125-106">However, removing the ACEs creates issues for Lync Server 2013 because it depends on read permissions to these containers to allow users to run domain preparation.</span></span>

<span data-ttu-id="c1125-107">在這種情況下，網域系統管理員群組中的成員資格是執行網域準備、伺服器啟用和池建立，不會再授與預設容器中所儲存之 Active Directory 資訊的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="c1125-107">In this situation, membership in the Domain Admins group, which is required to run domain preparation, server activation, and pool creation, no longer grants read access to Active Directory information stored in the default containers.</span></span> <span data-ttu-id="c1125-108">您必須在林根網域的各個容器上手動授與存取權，以檢查必備的目錄林準備程式是否已完成。</span><span class="sxs-lookup"><span data-stu-id="c1125-108">You must manually grant read-access permissions on various containers in the forest root domain to check that the prerequisite forest preparation procedure is complete.</span></span>

<span data-ttu-id="c1125-109">若要讓使用者在任何非林根網域上執行網域準備、伺服器啟用或池建立，您可以使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="c1125-109">To enable a user to run domain preparation, server activation, or pool creation on any non-forest root domain, you have the following options:</span></span>

  - <span data-ttu-id="c1125-110">使用企業系統管理員群組成員的帳戶來執行網域準備。</span><span class="sxs-lookup"><span data-stu-id="c1125-110">Use an account that is a member of the Enterprise Admins group to run domain preparation.</span></span>

  - <span data-ttu-id="c1125-111">使用網域系統管理員群組成員的帳戶，並在林根網域的下列每個容器中，授與此帳戶的讀取存取許可權：</span><span class="sxs-lookup"><span data-stu-id="c1125-111">Use an account that is a member of the Domain Admins group and grant this account read-access permissions on each of the following containers in the forest root domain:</span></span>
    
      - <span data-ttu-id="c1125-112">主域</span><span class="sxs-lookup"><span data-stu-id="c1125-112">Domain</span></span>
    
      - <span data-ttu-id="c1125-113">配置或系統</span><span class="sxs-lookup"><span data-stu-id="c1125-113">Configuration or System</span></span>

<span data-ttu-id="c1125-114">如果您不想使用企業系統管理員群組成員的帳戶來執行網域準備或其他設定工作，請明確授予您想要在林根的相關容器上使用 [讀取] 存取權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c1125-114">If you do not want to use an account that is a member of the Enterprise Admins group to run domain preparation or other Setup tasks, explicitly grant the account you want to use read access on the relevant containers in the forest root.</span></span>

<div>

## <a name="to-give-users-read-access-permissions-on-containers-in-the-forest-root-domain"></a><span data-ttu-id="c1125-115">在林根網域中為使用者提供對容器的讀取存取許可權</span><span class="sxs-lookup"><span data-stu-id="c1125-115">To give users read-access permissions on containers in the forest root domain</span></span>

1.  <span data-ttu-id="c1125-116">使用屬於林根網域之網域系統管理員群組成員的帳戶登入加入林根網域的電腦。</span><span class="sxs-lookup"><span data-stu-id="c1125-116">Log on to the computer joined to the forest root domain with an account that is a member of the Domain Admins group for the forest root domain.</span></span>

2.  <span data-ttu-id="c1125-117">針對目錄林根網域執行 adsiedit。</span><span class="sxs-lookup"><span data-stu-id="c1125-117">Run adsiedit.msc for the forest root domain.</span></span>
    
    <span data-ttu-id="c1125-118">如果從 [網域]、[設定] 或 [系統] 容器中移除經過驗證的使用者 Ace，您必須授與容器的唯讀許可權，如以下步驟所述。</span><span class="sxs-lookup"><span data-stu-id="c1125-118">If authenticated user ACEs were removed from the Domain, Configuration, or System container, you must grant read-only permissions to the container, as described in the following steps.</span></span>

3.  <span data-ttu-id="c1125-119">以滑鼠右鍵按一下容器，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="c1125-119">Right-click the container, and then click **Properties**.</span></span>

4.  <span data-ttu-id="c1125-120">按一下 [**安全性**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c1125-120">Click the **Security** tab.</span></span>

5.  <span data-ttu-id="c1125-121">按一下 [進階]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c1125-121">Click **Advanced**.</span></span>

6.  <span data-ttu-id="c1125-122">按一下 [**許可權**] 索引標籤上的 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c1125-122">On the **Permissions** tab, click **Add**.</span></span>

7.  <span data-ttu-id="c1125-123">使用下列格式，輸入接收許可權的使用者或群組的名稱： `domain\account name`，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c1125-123">Type the name of the user or group receiving permissions by using the following format: `domain\account name`, and then click **OK**.</span></span>

8.  <span data-ttu-id="c1125-124">在 [**物件**] 索引標籤上的 [**適用**于] 中，按一下 [**僅此物件**]。</span><span class="sxs-lookup"><span data-stu-id="c1125-124">On the **Objects** tab, in **Applies To**, click **This Object Only**.</span></span>

9.  <span data-ttu-id="c1125-125">在 [**許可權**] 中，按一下 [**允許**] 欄： [**清單內容**]、[**讀取所有屬性**] 和 [**讀取權限**]，以選取下列允許 ace。</span><span class="sxs-lookup"><span data-stu-id="c1125-125">In **Permissions**, select the following Allow ACEs by clicking the **Allow** column: **List Content**, **Read All Properties**, and **Read Permissions**.</span></span>

10. <span data-ttu-id="c1125-126">按一下 **[確定]** 兩次。</span><span class="sxs-lookup"><span data-stu-id="c1125-126">Click **OK** twice.</span></span>

11. <span data-ttu-id="c1125-127">針對步驟2中所列的任何相關容器，重複這些步驟。</span><span class="sxs-lookup"><span data-stu-id="c1125-127">Repeat these steps for any of the relevant containers listed in Step 2.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

