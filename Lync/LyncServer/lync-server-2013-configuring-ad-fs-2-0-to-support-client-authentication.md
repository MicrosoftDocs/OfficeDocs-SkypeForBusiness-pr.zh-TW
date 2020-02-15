---
title: Lync Server 2013： 設定 AD FS 2.0 以支援用戶端驗證
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring AD FS 2.0 to support client authentication
ms:assetid: 4d93d400-ccaa-4da8-a71b-d05d7ba79d93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308565(v=OCS.15)
ms:contentKeyID: 54973687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7054bae609b5d1a1c6fe176c1092614f5d30fa6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029704"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="3745b-102">設定 AD FS 2.0 以支援 Lync Server 2013 中的用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="3745b-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3745b-103">_**上次修改主題：** 2013年-07-03_</span><span class="sxs-lookup"><span data-stu-id="3745b-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="3745b-104">有兩種可能的驗證類型，可以設定為允許支援使用智慧卡驗證的 AD FS 2.0:</span><span class="sxs-lookup"><span data-stu-id="3745b-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="3745b-105">表單型驗證 (FBA)</span><span class="sxs-lookup"><span data-stu-id="3745b-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="3745b-106">傳輸層安全性用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="3745b-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="3745b-107">您可以使用表單型驗證，開發可讓使用者在驗證使用其使用者名稱與密碼，或使用他們智慧卡及 pin 碼的網頁。</span><span class="sxs-lookup"><span data-stu-id="3745b-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="3745b-108">本主題著重於如何實作傳輸層安全性用戶端 Authentication with AD FS 2.0。</span><span class="sxs-lookup"><span data-stu-id="3745b-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="3745b-109">如需 AD FS 2.0 驗證類型的詳細資訊，請參閱 AD FS 2.0： 如何變更本機驗證類型在[http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)。</span><span class="sxs-lookup"><span data-stu-id="3745b-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="3745b-110">**若要設定 AD FS 2.0 以支援用戶端驗證**</span><span class="sxs-lookup"><span data-stu-id="3745b-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="3745b-111">登入的 AD FS 2.0 使用網域系統管理員帳戶的電腦。</span><span class="sxs-lookup"><span data-stu-id="3745b-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="3745b-112">啟動 Windows 檔案總管]。</span><span class="sxs-lookup"><span data-stu-id="3745b-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="3745b-113">瀏覽至 c:\\inetpub\\adfs\\ls</span><span class="sxs-lookup"><span data-stu-id="3745b-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="3745b-114">讓現有的 web.config 檔案的備份複本。</span><span class="sxs-lookup"><span data-stu-id="3745b-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="3745b-115">開啟現有的 web.config 檔案，使用 [記事本]。</span><span class="sxs-lookup"><span data-stu-id="3745b-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="3745b-116">從 [功能表] 列中，選取 [**編輯**]，然後選取 [**尋找**。</span><span class="sxs-lookup"><span data-stu-id="3745b-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="3745b-117">搜尋**\<localAuthenticationTypes\>**。</span><span class="sxs-lookup"><span data-stu-id="3745b-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="3745b-118">請注意，有四種驗證類型所列，每行一個。</span><span class="sxs-lookup"><span data-stu-id="3745b-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="3745b-119">移動包含 TLSClient 驗證類型] 區段中的清單頂端的行。</span><span class="sxs-lookup"><span data-stu-id="3745b-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="3745b-120">儲存並關閉 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="3745b-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="3745b-121">啟動命令提示字元中使用提高的權限。</span><span class="sxs-lookup"><span data-stu-id="3745b-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="3745b-122">執行下列命令以重新啟動 IIS：</span><span class="sxs-lookup"><span data-stu-id="3745b-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

