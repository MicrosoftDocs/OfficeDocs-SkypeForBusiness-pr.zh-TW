---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc96ef027d63c5d2020bd52d55f378fcf7dacf51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503520"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="887c6-102">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="887c6-102">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="887c6-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="887c6-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="887c6-104">若要遷移撥入存取號碼，需要兩個步驟：執行 **Import-CsLegacyConfiguration** Cmdlet (在匯 [入原則和設定](import-policies-and-settings.md) 中完成，) 遷移撥號對應表及其他撥入存取號碼設定，以及執行 **Move-CsApplicationEndpoint** 指令程式以遷移連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="887c6-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="887c6-105">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="887c6-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="887c6-106">開啟 Office 通訊伺服器 2007 R2 系統管理工具。</span><span class="sxs-lookup"><span data-stu-id="887c6-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="887c6-107">在主控台樹狀目錄中，以滑鼠右鍵按一下樹系節點，並依序按一下 **[內容]** 和 **[會議服務員內容]**。</span><span class="sxs-lookup"><span data-stu-id="887c6-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="887c6-108">在 **[存取電話號碼]** 索引標籤上，按一下 **[由集區服務]**，依據其相關聯的集區排序存取電話號碼，並識別所移轉之集區的所有存取號碼。</span><span class="sxs-lookup"><span data-stu-id="887c6-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="887c6-109">若要識別每個存取號碼的 SIP URI，請按兩下存取號碼來開啟 **[編輯會議服務員號碼]** 對話方塊，然後查看 **[SIP URI]** 下方的內容。</span><span class="sxs-lookup"><span data-stu-id="887c6-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="887c6-110">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="887c6-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="887c6-111">若要將每個撥入存取號碼移至在 Lync Server 2013 上主控的集區，請執行：</span><span class="sxs-lookup"><span data-stu-id="887c6-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="887c6-112">在 [Office 通訊伺服器 2007 R2 系統管理工具] 的 [ **存取電話號碼** ] 索引標籤上，確認您要遷移的 Office 通訊伺服器 2007 R2 集區沒有任何撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="887c6-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

