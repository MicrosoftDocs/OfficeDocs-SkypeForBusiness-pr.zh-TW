---
title: Lync Server 2013：設定 AD FS 2.0 以支援用戶端驗證
description: Lync Server 2013：設定 AD FS 2.0 以支援用戶端驗證。
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
ms.openlocfilehash: 156eb6d7e8af85dec04601ab8f88c55181db20d5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553249"
---
# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="dcadc-103">設定 AD FS 2.0 以支援 Lync Server 2013 中的用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="dcadc-103">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcadc-104">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="dcadc-104">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="dcadc-105">有兩種可能的驗證類型可設定為允許 AD FS 2.0 支援使用智慧卡的驗證：</span><span class="sxs-lookup"><span data-stu-id="dcadc-105">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="dcadc-106">以表單為基礎的驗證 (FBA) </span><span class="sxs-lookup"><span data-stu-id="dcadc-106">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="dcadc-107">傳輸層安全性用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="dcadc-107">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="dcadc-108">使用以表單為基礎的驗證，您可以開發一個網頁，讓使用者可以使用其使用者名稱/密碼或使用智慧卡和 PIN 碼進行驗證。</span><span class="sxs-lookup"><span data-stu-id="dcadc-108">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="dcadc-109">本主題著重于如何使用 AD FS 2.0 來執行傳輸層安全性用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="dcadc-109">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="dcadc-110">如需 AD FS 2.0 驗證類型的相關資訊，請參閱 AD FS 2.0：如何變更本機驗證類型 [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384) 。</span><span class="sxs-lookup"><span data-stu-id="dcadc-110">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [https://go.microsoft.com/fwlink/p/?LinkId=313384](https://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="dcadc-111">**設定 AD FS 2.0 以支援用戶端驗證**</span><span class="sxs-lookup"><span data-stu-id="dcadc-111">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="dcadc-112">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="dcadc-112">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="dcadc-113">啟動 Windows Explorer。</span><span class="sxs-lookup"><span data-stu-id="dcadc-113">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="dcadc-114">流覽至 C： \\ inetpub \\ adfs \\ ls</span><span class="sxs-lookup"><span data-stu-id="dcadc-114">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="dcadc-115">請備份現有的 web.config 檔。</span><span class="sxs-lookup"><span data-stu-id="dcadc-115">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="dcadc-116">使用 [記事本] 開啟現有的 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="dcadc-116">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="dcadc-117">從功能表列中，選取 [ **編輯** ]，然後選取 [ **尋找**]。</span><span class="sxs-lookup"><span data-stu-id="dcadc-117">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="dcadc-118">搜尋 **\<localAuthenticationTypes\>** 。</span><span class="sxs-lookup"><span data-stu-id="dcadc-118">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="dcadc-119">請注意，列出了四種驗證類型，每行一個。</span><span class="sxs-lookup"><span data-stu-id="dcadc-119">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="dcadc-120">將包含 TLSClient 驗證類型的行移至區段中清單的頂端。</span><span class="sxs-lookup"><span data-stu-id="dcadc-120">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="dcadc-121">儲存並關閉 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="dcadc-121">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="dcadc-122">以較高的許可權啟動命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="dcadc-122">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="dcadc-123">執行下列命令以重新啟動 IIS：</span><span class="sxs-lookup"><span data-stu-id="dcadc-123">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

