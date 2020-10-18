---
title: Lync Server 2013：設定 Kerberos 驗證帳戶密碼
description: Lync Server 2013：設定 Kerberos 驗證帳戶密碼。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication account passwords
ms:assetid: b435f88e-4a77-4be7-b7e5-c17484303b74
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412870(v=OCS.15)
ms:contentKeyID: 48185167
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 614b1411f9454c39843f4e69cabbfc3b02986e51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577219"
---
# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="4c501-103">在 Lync Server 2013 中設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="4c501-103">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c501-104">_**主題上次修改日期：** 2010-11-03_</span><span class="sxs-lookup"><span data-stu-id="4c501-104">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="4c501-105">在您為 Kerberos 驗證帳戶建立電腦物件之後，您可以設定該帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="4c501-105">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="4c501-106">在一部伺服器上執行 Windows PowerShell Cmdlet 以設定 Kerberos 帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="4c501-106">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="4c501-107">您可以在您為 Kerberos 驗證建立的物件上設定密碼。</span><span class="sxs-lookup"><span data-stu-id="4c501-107">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="4c501-108">密碼可以設定為已知值，但預設為隨機密碼。</span><span class="sxs-lookup"><span data-stu-id="4c501-108">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="4c501-109">密碼可用於所有使用該帳戶的 Kerberos 驗證來源。</span><span class="sxs-lookup"><span data-stu-id="4c501-109">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="4c501-110">您可以使用 Windows PowerShell Cmdlet 來設定及管理 Kerberos 帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="4c501-110">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c501-111">Kerberos account 物件是電腦物件，但是會將 UserAccount 參數用於所參照 Windows PowerShell Cmdlet 中的 operations。</span><span class="sxs-lookup"><span data-stu-id="4c501-111">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="4c501-112">請注意，這不是錯誤，但搭配 Kerberos 帳戶建立及維護使用時的預定行為。</span><span class="sxs-lookup"><span data-stu-id="4c501-112">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4c501-113">本章節內容</span><span class="sxs-lookup"><span data-stu-id="4c501-113">In This Section</span></span>

  - [<span data-ttu-id="4c501-114">在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="4c501-114">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="4c501-115">在 Lync Server 2013 中同步處理 Kerberos 驗證帳戶密碼至 IIS</span><span class="sxs-lookup"><span data-stu-id="4c501-115">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

