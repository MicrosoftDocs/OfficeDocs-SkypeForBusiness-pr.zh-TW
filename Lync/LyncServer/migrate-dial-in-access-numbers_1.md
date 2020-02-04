---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a13fdf36dcd36dc71df8ffa06c273c2b2b0f0292
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="7831c-102">移轉撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="7831c-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7831c-103">_**主題上次修改日期：** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="7831c-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="7831c-104">遷移撥入存取號碼需要兩個步驟：執行**CsLegacyConfiguration** Cmdlet （在 [匯[入原則和設定](import-policies-and-settings.md)] 中完成），以遷移撥號方案及其他撥入存取號碼設定，並執行**移動 CsApplicationEndpoint** Cmdlet 來遷移連絡人物件。</span><span class="sxs-lookup"><span data-stu-id="7831c-104">Migrating dial-in access numbers requires two steps: running the **Import-CsLegacyConfiguration** cmdlet (completed earlier in [Import policies and settings](import-policies-and-settings.md)) to migrate dial plans and other dial-in access number settings, and running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span>

<div>

## <a name="to-migrate-dial-in-access-numbers"></a><span data-ttu-id="7831c-105">若要遷移撥入存取號碼</span><span class="sxs-lookup"><span data-stu-id="7831c-105">To migrate dial-in access numbers</span></span>

1.  <span data-ttu-id="7831c-106">開啟 Office 通訊伺服器 2007 R2 管理工具。</span><span class="sxs-lookup"><span data-stu-id="7831c-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="7831c-107">在主控台樹中，以滑鼠右鍵按一下 [林] 節點，按一下 [**屬性**]，然後按一下 [**會議助理屬性**]。</span><span class="sxs-lookup"><span data-stu-id="7831c-107">In the console tree, right-click the forest node, click **Properties**, and then click **Conferencing Attendant Properties**.</span></span>

3.  <span data-ttu-id="7831c-108">在 [**存取電話號碼**] 索引標籤上，按一下 [**依資源庫提供服務**]，依相關聯的池排序存取電話號碼，並找出您要從中遷移之池的所有存取號碼。</span><span class="sxs-lookup"><span data-stu-id="7831c-108">On the **Access Phone Numbers** tab, click **Serviced by Pool** to sort the access phone numbers by their associated pool, and identify all the access numbers for the pool from which you are migrating.</span></span>

4.  <span data-ttu-id="7831c-109">若要識別每個存取號碼的 SIP URI，請按兩下存取號碼以開啟 [**編輯會議助理編號**] 對話方塊，然後查看 [ **SIP URI**]。</span><span class="sxs-lookup"><span data-stu-id="7831c-109">To identify the SIP URI for each access number, double-click the access number to open the **Edit Conferencing Attendant Number** dialog box, and look under **SIP URI**.</span></span>

5.  <span data-ttu-id="7831c-110">開啟 Lync Server 管理命令介面。</span><span class="sxs-lookup"><span data-stu-id="7831c-110">Open the Lync Server Management Shell.</span></span>

6.  <span data-ttu-id="7831c-111">若要將每個撥入存取號碼移至 Lync Server 2013 上託管的池，請執行：</span><span class="sxs-lookup"><span data-stu-id="7831c-111">To move each dial-in access number to a pool hosted on Lync Server 2013, run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  <span data-ttu-id="7831c-112">在 Office 通訊伺服器 2007 R2 管理工具的 [**存取電話號碼**] 索引標籤上，確認您要從中遷移的 Office 通訊伺服器 2007 R2 池不會保留撥入存取號碼。</span><span class="sxs-lookup"><span data-stu-id="7831c-112">In the Office Communications Server 2007 R2 Administrative tool, on the **Access Phone Numbers** tab, verify that no dial-in access numbers remain for the Office Communications Server 2007 R2 pool from which you are migrating.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

