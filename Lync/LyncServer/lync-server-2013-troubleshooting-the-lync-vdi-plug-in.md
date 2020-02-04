---
title: Lync Server 2013：疑難排解 Lync VDI 外掛程式
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting the Lync VDI plug-in
ms:assetid: 183c9449-b907-409c-b5ed-b02af3bd93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204713(v=OCS.15)
ms:contentKeyID: 48183525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dfd8082ef0f0cdfc2a7931a675398507daaa51
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="1e955-102">在 Lync Server 2013 中疑難排解 Lync VDI 外掛程式</span><span class="sxs-lookup"><span data-stu-id="1e955-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e955-103">_**主題上次修改日期：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="1e955-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="1e955-104">在瘦用戶端上安裝 Lync VDI 外掛程式的疑難排解問題</span><span class="sxs-lookup"><span data-stu-id="1e955-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="1e955-105">如果您在瘦用戶端上安裝 VDI 外掛程式時會發生問題，請檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="1e955-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="1e955-106">確定您在 TEMP 及 TMP 系統變數中指定的資料夾中有足夠的空間。</span><span class="sxs-lookup"><span data-stu-id="1e955-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="1e955-107">確定已關閉 [防寫] 功能。</span><span class="sxs-lookup"><span data-stu-id="1e955-107">Ensure that write-protect is turned off.</span></span> <span data-ttu-id="1e955-108">如需相關指示，請參閱您的裝置製造商的檔。</span><span class="sxs-lookup"><span data-stu-id="1e955-108">Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="1e955-109">對配對問題進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="1e955-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="1e955-110">當 VDI 外掛程式配對失敗時，右下角的配對圖示會顯示為紅色的 [X]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1e955-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="1e955-111">![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")</span><span class="sxs-lookup"><span data-stu-id="1e955-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="1e955-112">下列是失敗的可能原因，以及您可以採取的修正動作。</span><span class="sxs-lookup"><span data-stu-id="1e955-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="1e955-113">**使用者在登入期間輸入的認證不正確。**</span><span class="sxs-lookup"><span data-stu-id="1e955-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="1e955-114">使用者應該登出 Lync，然後使用正確的認證重新登入。</span><span class="sxs-lookup"><span data-stu-id="1e955-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="1e955-115">[配對] 對話方塊會再次出現，並顯示配對是否成功。</span><span class="sxs-lookup"><span data-stu-id="1e955-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="1e955-116">**遠端桌面用戶端的另一個實例正在執行。**</span><span class="sxs-lookup"><span data-stu-id="1e955-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="1e955-117">如果他們是在 Windows 中使用 [遠端桌面連線]，使用者就應該執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1e955-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="1e955-118">啟動 [工作管理員]：按**Alt + Ctrl + Delete**，然後按一下 [**啟動工作管理員**]。</span><span class="sxs-lookup"><span data-stu-id="1e955-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="1e955-119">按一下 [**處理**程式] 索引標籤，然後在清單中尋找所有名為**mstsc**的進程。</span><span class="sxs-lookup"><span data-stu-id="1e955-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="1e955-120">醒目提示每個**mstsc**程式，然後按一下 [**結束處理**程式]。</span><span class="sxs-lookup"><span data-stu-id="1e955-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="1e955-121">啟動新的遠端桌面會話，然後再次嘗試連線。</span><span class="sxs-lookup"><span data-stu-id="1e955-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="1e955-122">**無法正確安裝所需的檔案。**</span><span class="sxs-lookup"><span data-stu-id="1e955-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="1e955-123">在本機電腦上安裝外掛程式之後，下列檔案應該出現在 C：\\Program Files\\Microsoft Office\\office 15 （或適當的磁片磁碟機號）下：</span><span class="sxs-lookup"><span data-stu-id="1e955-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="1e955-124">LyncVdiPlugin</span><span class="sxs-lookup"><span data-stu-id="1e955-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="1e955-125">UcVdi</span><span class="sxs-lookup"><span data-stu-id="1e955-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="1e955-126">如果 VDI 配對有任何問題，請檢查以確定本機電腦上是否有這些檔案。</span><span class="sxs-lookup"><span data-stu-id="1e955-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="1e955-127">**Lync 用戶端正在本機電腦上執行。**</span><span class="sxs-lookup"><span data-stu-id="1e955-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="1e955-128">若要使用 Lync VDI 外掛程式，不一定要在本機電腦上執行 Lync 用戶端，否則配對將會失敗。</span><span class="sxs-lookup"><span data-stu-id="1e955-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="1e955-129">最佳做法是，使用者不應該在本機電腦上安裝 Lync 用戶端。</span><span class="sxs-lookup"><span data-stu-id="1e955-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

