---
title: Lync Server 2013： 疑難排解 Lync VDI 外掛程式
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
ms.openlocfilehash: ddc58629ea7c641427347600be48538cd555022c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-the-lync-vdi-plug-in-in-lync-server-2013"></a><span data-ttu-id="757d6-102">疑難排解 Lync VDI 外掛程式 Lync Server 2013 中</span><span class="sxs-lookup"><span data-stu-id="757d6-102">Troubleshooting the Lync VDI plug-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="757d6-103">_**主題上次修改日期：** 2012年-10-10_</span><span class="sxs-lookup"><span data-stu-id="757d6-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<div>

## <a name="troubleshooting-issues-with-installing-the-lync-vdi-plug-in-on-a-thin-client"></a><span data-ttu-id="757d6-104">疑難排解在精簡型用戶端上安裝 Lync VDI 外掛程式的問題</span><span class="sxs-lookup"><span data-stu-id="757d6-104">Troubleshooting Issues with Installing the Lync VDI Plug-in on a Thin Client</span></span>

<span data-ttu-id="757d6-105">如果在精簡型用戶端上安裝 VDI 外掛程式時發生問題，請檢查下列各項：</span><span class="sxs-lookup"><span data-stu-id="757d6-105">If there are issues with installing the VDI plug-in on a thin client, check the following:</span></span>

  - <span data-ttu-id="757d6-106">確定您在 TEMP 和 TMP 系統變數中指定的資料夾中有足夠的空間。</span><span class="sxs-lookup"><span data-stu-id="757d6-106">Ensure that there is sufficient space in the folder that you specified in the TEMP and TMP system variables.</span></span>

  - <span data-ttu-id="757d6-p101">確定已關閉防寫保護。請參閱裝置製造商的文件，以取得指示。</span><span class="sxs-lookup"><span data-stu-id="757d6-p101">Ensure that write-protect is turned off. Refer to your device manufacturer’s documentation for instructions.</span></span>

</div>

<div>

## <a name="troubleshooting-issues-with-pairing"></a><span data-ttu-id="757d6-109">疑難排解配對問題</span><span class="sxs-lookup"><span data-stu-id="757d6-109">Troubleshooting Issues with Pairing</span></span>

<span data-ttu-id="757d6-110">當 VDI 外掛程式配對失敗時，右下的配對圖示會顯示成紅色的 “X”，如下所示：</span><span class="sxs-lookup"><span data-stu-id="757d6-110">When VDI plug-in pairing fails, the pairing icon in the lower right displays as a red “X” as shown:</span></span>

<span data-ttu-id="757d6-111">![顯示成功配對的 Lync VDI 圖示](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "顯示成功配對的 Lync VDI 圖示")</span><span class="sxs-lookup"><span data-stu-id="757d6-111">![Lync VDI icon showing successful pairing](images/JJ204948.303d618c-4bc8-41c4-8553-2475de0d395e(OCS.15).png "Lync VDI icon showing successful pairing")</span></span>

<span data-ttu-id="757d6-112">以下是失敗的可能原因，以及您可以採取的更正動作。</span><span class="sxs-lookup"><span data-stu-id="757d6-112">The following are possible reasons for failures and the corrective actions you can take.</span></span>

  - <span data-ttu-id="757d6-113">**使用者在登入時輸入不正確的憑證。**</span><span class="sxs-lookup"><span data-stu-id="757d6-113">**The user entered incorrect credentials during sign-in.**</span></span>
    
    <span data-ttu-id="757d6-114">使用者應該登出 Lync，然後再使用正確的認證登入。</span><span class="sxs-lookup"><span data-stu-id="757d6-114">The user should sign out of Lync and sign in again with the correct credentials.</span></span> <span data-ttu-id="757d6-115">配對對話方塊會重新出現，並顯示配對是否成功。</span><span class="sxs-lookup"><span data-stu-id="757d6-115">The pairing dialog box will reappear and show whether pairing is successful.</span></span>

  - <span data-ttu-id="757d6-116">**有另一個遠端桌面用戶端執行個體正在執行中。**</span><span class="sxs-lookup"><span data-stu-id="757d6-116">**Another instance of the remote desktop client is running.**</span></span>
    
    <span data-ttu-id="757d6-117">如果他們在 Windows 中使用遠端桌面連線，使用者應該執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="757d6-117">If they are using Remote Desktop Connection in Windows, users should do the following:</span></span>
    
    1.  <span data-ttu-id="757d6-118">啟動工作管理員：按 **Alt+Ctrl+Delete** 鍵，然後按一下 [啟動工作管理員]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="757d6-118">Start Task Manager: Press **Alt+Ctrl+Delete**, and then click **Start Task Manager**.</span></span>
    
    2.  <span data-ttu-id="757d6-119">按一下 [程序]\*\*\*\* 索引標籤，在清單中尋找名為 **mstsc.exe** 的所有程序。</span><span class="sxs-lookup"><span data-stu-id="757d6-119">Click the **Processes** tab and look for all processes named **mstsc.exe** in the list.</span></span>
    
    3.  <span data-ttu-id="757d6-120">將每個 **mstsc.exe** 程序醒目提示，然後按一下 [結束處理程序]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="757d6-120">Highlight each **mstsc.exe** process and then click **End Process**.</span></span>
    
    4.  <span data-ttu-id="757d6-121">啟動新的遠端桌面工作階段，並重試連線。</span><span class="sxs-lookup"><span data-stu-id="757d6-121">Start a new remote desktop session and try connecting again.</span></span>

  - <span data-ttu-id="757d6-122">**必要檔案安裝不正確。**</span><span class="sxs-lookup"><span data-stu-id="757d6-122">**The necessary files did not install correctly.**</span></span>
    
    <span data-ttu-id="757d6-123">外掛程式安裝在本機電腦上之後，下列檔案應出現 [c:\\Program Files\\Microsoft Office\\Office15 （或適當的磁碟機代號）：</span><span class="sxs-lookup"><span data-stu-id="757d6-123">After the plug-in is installed on the local computer, the following files should be present under C:\\Program Files\\Microsoft Office\\Office15 (or the appropriate drive letter):</span></span>
    
      - <span data-ttu-id="757d6-124">LyncVdiPlugin.dll</span><span class="sxs-lookup"><span data-stu-id="757d6-124">LyncVdiPlugin.dll</span></span>
    
      - <span data-ttu-id="757d6-125">UcVdi.dll</span><span class="sxs-lookup"><span data-stu-id="757d6-125">UcVdi.dll</span></span>
    
    <span data-ttu-id="757d6-126">如果 VDI 配對有任何問題，請檢查並確定這些檔案存在於本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="757d6-126">If there are any issues with VDI pairing, check to make sure that these files are present on the local computer.</span></span>

  - <span data-ttu-id="757d6-127">**Lync 用戶端正在本機電腦上執行。**</span><span class="sxs-lookup"><span data-stu-id="757d6-127">**The Lync client is running on the local computer.**</span></span>
    
    <span data-ttu-id="757d6-128">若要使用的 Lync VDI 外掛程式，Lync 用戶端必須未執行的本機電腦，否則配對將會失敗。</span><span class="sxs-lookup"><span data-stu-id="757d6-128">To use the Lync VDI plugin, a Lync client must not be running on the local computer, otherwise pairing will fail.</span></span> <span data-ttu-id="757d6-129">最佳作法是，使用者不應該安裝 Lync 用戶端的本機電腦上。</span><span class="sxs-lookup"><span data-stu-id="757d6-129">As a best practice, the user should not install a Lync client on the local computer.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

