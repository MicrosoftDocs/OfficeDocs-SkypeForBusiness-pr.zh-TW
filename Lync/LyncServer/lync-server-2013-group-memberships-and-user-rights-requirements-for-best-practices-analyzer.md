---
title: 最佳做法分析程式的群組成員資格與使用者權利需求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2c60f6256cead59b16f443994143d40bdbc00393
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="01c88-102">Lync Server 2013 中最佳做法分析程式的群組成員資格與使用者權利需求</span><span class="sxs-lookup"><span data-stu-id="01c88-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01c88-103">_**主題上次修改日期：** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="01c88-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="01c88-104">若要成功執行最佳做法分析程式，您用來登入的使用者帳戶必須是本機電腦上系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="01c88-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="01c88-105">此外，若要掃描您的環境，使用者帳戶必須是下列群組的成員：</span><span class="sxs-lookup"><span data-stu-id="01c88-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="01c88-106">**[網域管理員**   ] 可列舉 Active Directory 網域服務資訊，並在網網域控制站和通用類別目錄伺服器上呼叫 Windows Management Instrumentation （WMI）提供者。</span><span class="sxs-lookup"><span data-stu-id="01c88-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="01c88-107">\*\*\*\*    每個 Lync server 2013 內部電腦和每個邊緣伺服器所需的管理員都要呼叫 Windows Management Instrumentation （WMI）提供者，並存取登錄。</span><span class="sxs-lookup"><span data-stu-id="01c88-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="01c88-108">**RTCUniversalReadOnlyAdmins**   完整或委派的唯讀 Lync Server 2013 系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="01c88-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="01c88-109">**Exchange 僅適用**   于 Microsoft exchange 組織中的 [僅限系統管理員完全查看] 或 [委派 exchange Exchange 的管理員]。</span><span class="sxs-lookup"><span data-stu-id="01c88-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="01c88-110">如果您的使用者帳戶沒有足夠的使用者許可權，您有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="01c88-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="01c88-111">在命令提示字元中，使用**runas**命令，在擁有足夠使用者許可權的帳戶下執行該工具。</span><span class="sxs-lookup"><span data-stu-id="01c88-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="01c88-112">語法如下所示：</span><span class="sxs-lookup"><span data-stu-id="01c88-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="01c88-113">在 [連線**至 Active Directory]** 頁面上，設定您打算用來執行最佳做法分析程式的帳號憑證。</span><span class="sxs-lookup"><span data-stu-id="01c88-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="01c88-114">按一下 **[顯示高級登入選項**]。</span><span class="sxs-lookup"><span data-stu-id="01c88-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="01c88-115">您可以輸入三個帳戶：一個用於連線至 Active Directory 網域服務，一個用於連線至 Lync Server 2013 Edge 伺服器，另一個用於連線到 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="01c88-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="01c88-116">如果您沒有指定任何這些帳戶，就會使用您用來登入和執行最佳做法分析程式的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="01c88-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

