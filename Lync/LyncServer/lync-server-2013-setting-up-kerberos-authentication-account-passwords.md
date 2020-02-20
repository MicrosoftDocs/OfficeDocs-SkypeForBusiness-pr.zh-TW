---
title: Lync Server 2013： 設定 Kerberos 驗證帳戶密碼
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
ms.openlocfilehash: bef30a82479c876dbb4b4e6e6e9b55b3c2b37dc3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-account-passwords-in-lync-server-2013"></a><span data-ttu-id="b772f-102">設定 Lync Server 2013 中的 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="b772f-102">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b772f-103">_**主題上次修改日期：** 2010年-11-03_</span><span class="sxs-lookup"><span data-stu-id="b772f-103">_**Topic Last Modified:** 2010-11-03_</span></span>

<span data-ttu-id="b772f-104">建立 Kerberos 驗證帳戶的電腦物件之後，您可以設定帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="b772f-104">After you create the computer object for the Kerberos authentication account, you can set up the password for the account.</span></span> <span data-ttu-id="b772f-105">您在執行 Windows PowerShell cmdlet，在一部伺服器上設定 Kerberos 帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="b772f-105">You run the Windows PowerShell cmdlet for setting the Kerberos account password on one server.</span></span> <span data-ttu-id="b772f-106">您可以在您建立的 Kerberos 驗證的物件上設定密碼。</span><span class="sxs-lookup"><span data-stu-id="b772f-106">You can set the password on the object that you created for the Kerberos authentication.</span></span> <span data-ttu-id="b772f-107">密碼可以設為已知的值，但預設會選取隨機密碼。</span><span class="sxs-lookup"><span data-stu-id="b772f-107">The password can be set to a known value, but by default is a random password.</span></span> <span data-ttu-id="b772f-108">Password 是可使用之帳戶的所有 Kerberos 驗證來源。</span><span class="sxs-lookup"><span data-stu-id="b772f-108">The password is available to all Kerberos authentication sources that use the account.</span></span> <span data-ttu-id="b772f-109">您可以使用 Windows PowerShell cmdlet 設定及管理 Kerberos 帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="b772f-109">You use Windows PowerShell cmdlets to set up and manage Kerberos account passwords.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b772f-110">Kerberos 帳戶物件是電腦物件，但使用 UserAccount 參數所參考的 Windows PowerShell cmdlet 中的作業。</span><span class="sxs-lookup"><span data-stu-id="b772f-110">The Kerberos account object is a computer object, but uses the UserAccount parameter for operations in the Windows PowerShell cmdlets that are referenced.</span></span> <span data-ttu-id="b772f-111">請注意這不是發生錯誤，但指令程式的 Kerberos 帳戶建立和維護搭配使用時的預期的行為。</span><span class="sxs-lookup"><span data-stu-id="b772f-111">Note that this is not a mistake, but the intended behavior of the cmdlet when used with the Kerberos account creation and maintenance.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b772f-112">本章節內容</span><span class="sxs-lookup"><span data-stu-id="b772f-112">In This Section</span></span>

  - [<span data-ttu-id="b772f-113">在 Lync Server 2013 中的伺服器上設定 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="b772f-113">Set a Kerberos authentication account password on a server in Lync Server 2013</span></span>](lync-server-2013-set-a-kerberos-authentication-account-password-on-a-server.md)

  - [<span data-ttu-id="b772f-114">同步處理 Lync Server 2013 中的 IIS 的 Kerberos 驗證帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="b772f-114">Synchronize a Kerberos authentication account password to IIS in Lync Server 2013</span></span>](lync-server-2013-synchronize-a-kerberos-authentication-account-password-to-iis.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

