---
title: Lync Server 2013： 設定 Kerberos 驗證
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
ms.openlocfilehash: d8ae852be13ee1ca7780ed89bf710e64fe5a2902
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="32a30-102">設定 Lync Server 2013 中的 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="32a30-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32a30-103">_**上次修改主題：** 2013年-02-21_</span><span class="sxs-lookup"><span data-stu-id="32a30-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="32a30-104">Lync Server 2013 支援 NTLM 和 Kerberos 驗證的 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="32a30-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="32a30-105">Office Communications Server 2007 和 Office Communications Server 2007 R2 做為預設 RTCComponentService 和 RTCService 的使用者帳戶來執行 Web 服務應用程式集區，指派給使用者，讓服務主體名稱 (SPN)帳戶和做為驗證主體。</span><span class="sxs-lookup"><span data-stu-id="32a30-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="32a30-106">Lync Server 會使用 NetworkService 若要執行 Web 服務和 NetworkService 不能有指派給它的 Spn。</span><span class="sxs-lookup"><span data-stu-id="32a30-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="32a30-107">若要解決問題： 不保留 Spn 的 Active Directory 物件，Lync Server Control Panel 可以達到此目的使用電腦 account 物件。</span><span class="sxs-lookup"><span data-stu-id="32a30-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="32a30-108">電腦帳戶物件可以保留的 Spn，並不會受到密碼到期，已使用在舊版中的使用者帳戶的問題。</span><span class="sxs-lookup"><span data-stu-id="32a30-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="32a30-109">您可以使用 Windows PowerShell cmdlet 來設定電腦物件，以提供 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="32a30-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="32a30-110">本章節內容</span><span class="sxs-lookup"><span data-stu-id="32a30-110">In This Section</span></span>

  - [<span data-ttu-id="32a30-111">啟用 Lync Server 2013 中的 Kerberos 驗證的必要條件</span><span class="sxs-lookup"><span data-stu-id="32a30-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="32a30-112">在 Lync Server 2013 中建立的 Kerberos 驗證帳戶</span><span class="sxs-lookup"><span data-stu-id="32a30-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="32a30-113">將 Kerberos 驗證帳戶指派給 Lync Server 2013 中的網站</span><span class="sxs-lookup"><span data-stu-id="32a30-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="32a30-114">設定 Lync Server 2013 中的 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="32a30-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="32a30-115">Lync Server 2013 中將 Kerberos 驗證新增到其他站台</span><span class="sxs-lookup"><span data-stu-id="32a30-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="32a30-116">Lync Server 2013 中從網站移除 Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="32a30-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - <span data-ttu-id="32a30-117">[測試和報告 [狀態] 和 [工作分派的 Lync Server 2013 中的 Kerberos 驗證](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="32a30-117">[Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

