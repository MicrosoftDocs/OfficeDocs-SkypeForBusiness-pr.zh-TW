---
title: 最佳做法分析程式的群組成員資格和使用者權限需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a72a7fdc73aeda96a2875ac48fd51b6023ddba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506070"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="a993f-102">Lync Server 2013 中最佳做法分析程式的群組成員資格和使用者權限需求</span><span class="sxs-lookup"><span data-stu-id="a993f-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a993f-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a993f-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a993f-104">若要成功執行最佳做法分析程式，您用來登入的使用者帳戶必須是本機電腦上管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="a993f-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="a993f-105">此外，若要掃描您的環境，使用者帳戶必須是下列群組的成員：</span><span class="sxs-lookup"><span data-stu-id="a993f-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="a993f-106">**Domain Admins**    若要列舉 Active Directory 網域服務資訊，並呼叫 Windows Management Instrumentation (WMI) 提供者的網域控制站和通用類別目錄伺服器。</span><span class="sxs-lookup"><span data-stu-id="a993f-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="a993f-107">**管理員**    在每一部 Lync Server 2013 內部電腦及每一部 Edge Server 上都是必要的，可呼叫 Windows Management Instrumentation (WMI) 提供者和存取登錄。</span><span class="sxs-lookup"><span data-stu-id="a993f-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="a993f-108">**RTCUniversalReadOnlyAdmins**    已滿或已委派唯讀 Lync Server 2013 系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="a993f-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="a993f-109">**僅限 Exchange View 系統管理員**    「完全」或「委派 Exchange」只查看 Microsoft Exchange 組織的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="a993f-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="a993f-110">如果您的使用者帳戶沒有足夠的使用者權限，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="a993f-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="a993f-111">在命令提示字元下，使用 **runas** 命令，以具備足夠使用者權限的帳戶來執行工具。</span><span class="sxs-lookup"><span data-stu-id="a993f-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="a993f-112">語法如下所示：</span><span class="sxs-lookup"><span data-stu-id="a993f-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="a993f-113">在 [連線 **至 Active Directory]** 頁面上，設定您計畫用以執行最佳做法分析程式的帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="a993f-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="a993f-114">按一下 **[顯示高級登入選項**]。</span><span class="sxs-lookup"><span data-stu-id="a993f-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="a993f-115">您可以輸入三個帳戶：一個用於連線至 Active Directory 網域服務，一個用於連線至 Lync Server 2013 Edge server，另一個則用於連接至 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a993f-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="a993f-116">如果您未指定任何這些帳戶，則會使用您用來登入和執行最佳做法分析程式的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="a993f-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

