---
title: Lync Server 2013：設定 AD FS 2.0 以支援用戶端驗證
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
ms.openlocfilehash: c7fe9587e85ad300a212e4a8199fa4a8a48d1877
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-ad-fs-20-to-support-client-authentication-in-lync-server-2013"></a><span data-ttu-id="d5eb7-102">在 Lync Server 2013 中設定 AD FS 2.0 以支援用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="d5eb7-102">Configuring AD FS 2.0 to support client authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5eb7-103">_**主題上次修改日期：** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="d5eb7-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="d5eb7-104">有兩種可能的驗證類型可以設定為允許 AD FS 2.0 使用智慧卡支援驗證：</span><span class="sxs-lookup"><span data-stu-id="d5eb7-104">There are two possible authentication types that can be configured to allow AD FS 2.0 to support authentication using smart cards:</span></span>

  - <span data-ttu-id="d5eb7-105">以表單為基礎的驗證（FBA）</span><span class="sxs-lookup"><span data-stu-id="d5eb7-105">Forms-based authentication (FBA)</span></span>

  - <span data-ttu-id="d5eb7-106">傳輸層安全性用戶端驗證</span><span class="sxs-lookup"><span data-stu-id="d5eb7-106">Transport Layer Security Client Authentication</span></span>

<span data-ttu-id="d5eb7-107">使用以表單為基礎的驗證，您可以開發網頁，讓使用者可以使用他們的使用者名稱/密碼或使用其智慧卡和 PIN 來進行驗證。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-107">Using forms-based authentication, you can develop a web page that allows users to authenticate either by using their username/password or by using their smart card and PIN.</span></span> <span data-ttu-id="d5eb7-108">本主題重點說明如何使用 AD FS 2.0 來實現傳輸層安全性用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-108">This topic focuses on how to implement Transport Layer Security Client Authentication with AD FS 2.0.</span></span> <span data-ttu-id="d5eb7-109">如需有關 AD FS 2.0 驗證類型的詳細資訊，請參閱 AD FS 2.0：如何變更本機驗證類型[http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384)。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-109">For more information about AD FS 2.0 authentication types, see AD FS 2.0: How to Change the Local Authentication Type at [http://go.microsoft.com/fwlink/p/?LinkId=313384](http://go.microsoft.com/fwlink/p/?linkid=313384).</span></span>

<div>


<span data-ttu-id="d5eb7-110">**設定 AD FS 2.0 以支援用戶端驗證**</span><span class="sxs-lookup"><span data-stu-id="d5eb7-110">**To Configure AD FS 2.0 to Support Client Authentication**</span></span>

1.  <span data-ttu-id="d5eb7-111">使用網域系統管理員帳戶登入 AD FS 2.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-111">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="d5eb7-112">啟動 Windows 資源管理器。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-112">Launch Windows Explorer.</span></span>

3.  <span data-ttu-id="d5eb7-113">流覽至 C：\\inetpub\\adfs\\ls</span><span class="sxs-lookup"><span data-stu-id="d5eb7-113">Browse to C:\\inetpub\\adfs\\ls</span></span>

4.  <span data-ttu-id="d5eb7-114">製作現有 web.config 檔案的備份複本。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-114">Make a backup copy of the existing web.config file.</span></span>

5.  <span data-ttu-id="d5eb7-115">使用記事本開啟現有的 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-115">Open the existing web.config file using Notepad.</span></span>

6.  <span data-ttu-id="d5eb7-116">從功能表列中，選取 [**編輯**]，然後選取 [**尋找**]。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-116">From the Menu bar, select **Edit** and then select **Find**.</span></span>

7.  <span data-ttu-id="d5eb7-117">搜尋\*\* \<localAuthenticationTypes\>\*\*。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-117">Search for **\<localAuthenticationTypes\>**.</span></span>
    
    <span data-ttu-id="d5eb7-118">請注意，列出四個驗證類型，每行一個。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-118">Note that there are four authentication types listed, one per line.</span></span>

8.  <span data-ttu-id="d5eb7-119">將包含 TLSClient 驗證類型的行移至區段中清單的頂端。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-119">Move the line containing the TLSClient authentication type to the top of the list in the section.</span></span>

9.  <span data-ttu-id="d5eb7-120">儲存並關閉 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-120">Save and Close the web.config file.</span></span>

10. <span data-ttu-id="d5eb7-121">以較高的許可權啟動命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="d5eb7-121">Launch a Command Prompt with elevated privileges.</span></span>

11. <span data-ttu-id="d5eb7-122">執行下列命令以重新開機 IIS：</span><span class="sxs-lookup"><span data-stu-id="d5eb7-122">Restart IIS by running the following command:</span></span>
    
        IISReset /Restart /NoForce

</div>

</div>

<span> </span>

</div>

</div>

</div>

