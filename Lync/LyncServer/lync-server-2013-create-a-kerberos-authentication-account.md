---
title: Lync Server 2013：建立 Kerberos 驗證帳戶
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a Kerberos authentication account
ms:assetid: 63f0cef6-562a-4209-ae25-71f8dc7c7295
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398449(v=OCS.15)
ms:contentKeyID: 48184348
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ab4f93d4204f7ed1f2b22d27ddb51328f8330c5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-kerberos-authentication-account-in-lync-server-2013"></a><span data-ttu-id="f6305-102">在 Lync Server 2013 中建立 Kerberos 驗證帳戶</span><span class="sxs-lookup"><span data-stu-id="f6305-102">Create a Kerberos authentication account in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6305-103">_**主題上次修改日期：** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="f6305-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="f6305-104">若要成功完成此程式，您必須以網域管理員群組的成員的身分登入伺服器或網域。</span><span class="sxs-lookup"><span data-stu-id="f6305-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group.</span></span>

<span data-ttu-id="f6305-105">您可以為每個網站建立 Kerberos 驗證帳戶，或者您可以建立單一 Kerberos 驗證帳戶並將它用於所有網站。</span><span class="sxs-lookup"><span data-stu-id="f6305-105">You can create Kerberos authentication accounts for each site or you can create a single Kerberos authentication account and use it for all sites.</span></span> <span data-ttu-id="f6305-106">您可以使用 Windows PowerShell Cmdlet 來建立及管理帳戶，包括識別指派給每個網站的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f6305-106">You use Windows PowerShell cmdlets to create and manage the accounts, including identifying the accounts assigned to each site.</span></span> <span data-ttu-id="f6305-107">拓撲建立器和 Lync Server 2013 [控制台] 不會顯示 Kerberos 驗證帳戶。</span><span class="sxs-lookup"><span data-stu-id="f6305-107">Topology Builder and the Lync Server 2013 Control Panel do not display Kerberos authentication accounts.</span></span> <span data-ttu-id="f6305-108">使用下列程式建立一個或多個用來進行 Kerberos 驗證的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="f6305-108">Use the following procedure to create one or more user accounts to be used for Kerberos authentication.</span></span>

<div>

## <a name="to-create-a-kerberos-account"></a><span data-ttu-id="f6305-109">建立 Kerberos 帳戶</span><span class="sxs-lookup"><span data-stu-id="f6305-109">To create a Kerberos account</span></span>

1.  <span data-ttu-id="f6305-110">做為 Domain Admins 群組的成員，請登入執行 Lync Server 2013 的網域中的電腦，或登入安裝管理工具的電腦。</span><span class="sxs-lookup"><span data-stu-id="f6305-110">As a member of the Domain Admins group, log on to a computer in the domain running Lync Server 2013 or on to a computer where the administrative tools are installed.</span></span>

2.  <span data-ttu-id="f6305-111">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f6305-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f6305-112">從命令列執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="f6305-112">From the command line, run the following command:</span></span>
    
        New-CsKerberosAccount -UserAccount "Domain\UserAccount" -ContainerDN "CN=Users,DC=DomainName,DC=DomainExtension"
    
    <span data-ttu-id="f6305-113">例如：</span><span class="sxs-lookup"><span data-stu-id="f6305-113">For example:</span></span>
    
        New-CsKerberosAccount -UserAccount "Contoso\KerbAuth" -ContainerDN "CN=Users,DC=contoso,DC=com"

4.  <span data-ttu-id="f6305-114">若要確認電腦物件是透過開啟 Active Directory 使用者和電腦來建立，請展開 [**使用者**] 容器，然後確認使用者帳戶的電腦物件位於容器中。</span><span class="sxs-lookup"><span data-stu-id="f6305-114">Confirm that the Computer object was created by opening Active Directory User and Computers, expand the **Users** container, and then confirm that the Computer object for the user account is in the container.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

