---
title: Lync Server 2013：設定 Kerberos 驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86526b40ee837866cdf0e3b016a8e4e627ca2eef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="08afb-102">在 Lync Server 2013 中設定 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="08afb-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08afb-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="08afb-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="08afb-104">Lync Server 2013 支援針對 Web 服務進行 NTLM 和 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="08afb-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="08afb-105">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 使用預設的 RTCComponentService 和 RTCService 作為使用者帳戶來執行 Web 服務應用程式池，允許將服務主體名稱（SPN）指派給使用者帳戶並充當驗證原則。</span><span class="sxs-lookup"><span data-stu-id="08afb-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="08afb-106">Lync Server 使用 NetworkService 來執行 Web 服務，而 NetworkService 不能指派 Spn 給它。</span><span class="sxs-lookup"><span data-stu-id="08afb-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="08afb-107">為了解決沒有 Active Directory 物件來保留 Spn 的問題，Lync Server [控制台] 可以使用電腦帳戶物件來達到此目的。</span><span class="sxs-lookup"><span data-stu-id="08afb-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="08afb-108">電腦帳戶物件可以保留 Spn，而且不受密碼到期的限制，這是在舊版中使用使用者帳戶的問題。</span><span class="sxs-lookup"><span data-stu-id="08afb-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="08afb-109">您可以使用 Windows PowerShell Cmdlet 來設定電腦物件，以提供 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="08afb-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="08afb-110">本節內容</span><span class="sxs-lookup"><span data-stu-id="08afb-110">In This Section</span></span>

  - [<span data-ttu-id="08afb-111">在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件</span><span class="sxs-lookup"><span data-stu-id="08afb-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="08afb-112">在 Lync Server 2013 中建立 Kerberos 驗證帳戶</span><span class="sxs-lookup"><span data-stu-id="08afb-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="08afb-113">在 Lync Server 2013 中將 Kerberos 驗證帳戶指派到網站</span><span class="sxs-lookup"><span data-stu-id="08afb-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="08afb-114">在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="08afb-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="08afb-115">在 Lync Server 2013 中新增 Kerberos 驗證至其他站台</span><span class="sxs-lookup"><span data-stu-id="08afb-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="08afb-116">在 Lync Server 2013 中從網站移除 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="08afb-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="08afb-117">在 Lync Server 2013 中測試和報告 Kerberos 驗證的狀態和指派</span><span class="sxs-lookup"><span data-stu-id="08afb-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

