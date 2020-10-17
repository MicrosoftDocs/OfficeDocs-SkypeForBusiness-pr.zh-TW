---
title: Lync Server 2013：設定 Kerberos 驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4f354d985ed9e0fc85909e232e06e7c34dd593
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509650"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="7763a-102">在 Lync Server 2013 中設定 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="7763a-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7763a-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="7763a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="7763a-104">Lync Server 2013 支援 Web 服務的 NTLM 和 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="7763a-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="7763a-105">Office 通訊伺服器2007和 Office 通訊伺服器 2007 R2 使用預設的 RTCComponentService 和 RTCService 作為使用者帳戶，以執行 Web 服務應用程式集區，讓服務主體名稱 (SPN) 指派給使用者帳戶，並作為驗證主體。</span><span class="sxs-lookup"><span data-stu-id="7763a-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="7763a-106">Lync Server 會使用 NetworkService 來執行 Web 服務，且 NetworkService 不能有指派給它的 Spn。</span><span class="sxs-lookup"><span data-stu-id="7763a-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="7763a-107">為了解決未讓 Active Directory 物件保留 Spn 的問題，Lync Server 控制台可以使用電腦帳戶物件來進行此專案的。</span><span class="sxs-lookup"><span data-stu-id="7763a-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="7763a-108">電腦帳戶物件可以保留 Spn，但不受密碼到期的限制，這是在舊版中使用使用者帳戶時發生的問題。</span><span class="sxs-lookup"><span data-stu-id="7763a-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="7763a-109">您可以使用 Windows PowerShell Cmdlet 來設定電腦物件，以提供 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="7763a-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7763a-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="7763a-110">In This Section</span></span>

  - [<span data-ttu-id="7763a-111">在 Lync Server 2013 中啟用 Kerberos 驗證的先決條件</span><span class="sxs-lookup"><span data-stu-id="7763a-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="7763a-112">在 Lync Server 2013 中建立 Kerberos 驗證帳戶</span><span class="sxs-lookup"><span data-stu-id="7763a-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="7763a-113">在 Lync Server 2013 中指派 Kerberos 驗證帳戶至網站</span><span class="sxs-lookup"><span data-stu-id="7763a-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="7763a-114">在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="7763a-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="7763a-115">在 Lync Server 2013 中，新增 Kerberos 驗證至其他網站</span><span class="sxs-lookup"><span data-stu-id="7763a-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="7763a-116">在 Lync Server 2013 中，移除網站的 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="7763a-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="7763a-117">在 Lync Server 2013 中測試和報告 Kerberos 驗證的狀態和指派</span><span class="sxs-lookup"><span data-stu-id="7763a-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

