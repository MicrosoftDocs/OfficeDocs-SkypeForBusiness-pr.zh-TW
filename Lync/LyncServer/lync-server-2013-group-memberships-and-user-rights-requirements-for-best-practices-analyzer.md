---
title: 群組的成員資格和最佳做法分析程式的使用者權限需求
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
ms.openlocfilehash: b552f9aadfe9ed4c99c12b7e3f9524e4de143e23
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a><span data-ttu-id="fedd2-102">群組的成員資格和 Lync Server 2013 中的最佳做法分析程式的使用者權限需求</span><span class="sxs-lookup"><span data-stu-id="fedd2-102">Group memberships and user rights requirements for Best Practices Analyzer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fedd2-103">_**主題上次修改日期：** 2012年-10-21_</span><span class="sxs-lookup"><span data-stu-id="fedd2-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="fedd2-104">若要成功執行 Best Practices Analyzer，您用來登入的使用者帳戶必須是本機電腦上管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="fedd2-104">To successfully run Best Practices Analyzer, the user account that you use to log on must be a member of the Administrators group on the local computer.</span></span> <span data-ttu-id="fedd2-105">此外，來掃描您的環境，使用者帳戶必須是下列群組的成員：</span><span class="sxs-lookup"><span data-stu-id="fedd2-105">Additionally, to scan your environment, the user account must be a member of the following groups:</span></span>

  - <span data-ttu-id="fedd2-106">**以 domain Admins**   列舉 Active Directory 網域服務的資訊，以及如何呼叫 Windows Management Instrumentation (WMI) 提供者在網域控制站和通用類別目錄伺服器。</span><span class="sxs-lookup"><span data-stu-id="fedd2-106">**Domain Admins**   To enumerate Active Directory Domain Services information and to call the Windows Management Instrumentation (WMI) providers on domain controllers and global catalog servers.</span></span>

  - <span data-ttu-id="fedd2-107">**系統管理員**   呼叫 Windows Management Instrumentation (WMI) 提供者及存取登錄，每個 Lync Server 2013 內部電腦與每部 Edge Server 所需。</span><span class="sxs-lookup"><span data-stu-id="fedd2-107">**Administrators**   Required on each Lync Server 2013 internal computer and each Edge Server to call the Windows Management Instrumentation (WMI) providers and to access the registry.</span></span>

  - <span data-ttu-id="fedd2-108">**RTCUniversalReadOnlyAdmins**   完整或委派讀取唯一的 Lync Server 2013 系統管理權限。</span><span class="sxs-lookup"><span data-stu-id="fedd2-108">**RTCUniversalReadOnlyAdmins**   Full or delegated read only Lync Server 2013 administrative rights.</span></span>

  - <span data-ttu-id="fedd2-109">**Exchange 檢視僅限系統管理員**   完整或委派 Exchange 檢視僅限系統管理員在 Microsoft Exchange 組織。</span><span class="sxs-lookup"><span data-stu-id="fedd2-109">**Exchange View Only Administrator**   Full or delegated Exchange View Only Administrator on the Microsoft Exchange organization.</span></span>

<span data-ttu-id="fedd2-110">如果您的使用者帳戶沒有足夠的權限，您會有兩個選項：</span><span class="sxs-lookup"><span data-stu-id="fedd2-110">If your user account does not have sufficient user rights, you have two options:</span></span>

  - <span data-ttu-id="fedd2-111">在命令提示字元處，執行另一個帳戶沒有足夠的權限工具使用**runas**命令。</span><span class="sxs-lookup"><span data-stu-id="fedd2-111">At a command prompt, use the **runas** command to run the tool under an account that does have sufficient user rights.</span></span> <span data-ttu-id="fedd2-112">語法如下所示：</span><span class="sxs-lookup"><span data-stu-id="fedd2-112">The syntax is as follows:</span></span>
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - <span data-ttu-id="fedd2-113">在 [ **Active directory Connect** ] 頁面上，設定想要用來執行最佳做法分析程式的帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="fedd2-113">On the **Connect to Active Directory** page, set the credentials for the accounts that you plan to use to run Best Practices Analyzer.</span></span> <span data-ttu-id="fedd2-114">按一下 [**顯示進階登入選項**]。</span><span class="sxs-lookup"><span data-stu-id="fedd2-114">Click **Show advanced login options**.</span></span> <span data-ttu-id="fedd2-115">您可以輸入三個帳戶： 一個用於連線至 Active Directory 網域服務、 另一個適用於連線至 Lync Server 2013 Edge Server，和另一個適用於連線至 Exchange 伺服器。</span><span class="sxs-lookup"><span data-stu-id="fedd2-115">You can enter three accounts: one for connecting to Active Directory Domain Services, one for connecting to Lync Server 2013 Edge Servers, and one for connecting to the Exchange Servers.</span></span> <span data-ttu-id="fedd2-116">如果您未指定任何這些帳戶，會使用您用來登入，並執行 Best Practices Analyzer 的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="fedd2-116">If you do not specify any of these accounts, the user account that you used to log on and run Best Practices Analyzer is used.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

