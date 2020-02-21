---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: ac7f0f39-4c6d-4702-8e25-93a73e3d800f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205160(v=OCS.15)
ms:contentKeyID: 48185064
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 42d28161eab03d494dd5ebb3771c0879dd3dbb99
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="e8a3e-102">移轉通訊錄</span><span class="sxs-lookup"><span data-stu-id="e8a3e-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8a3e-103">_**主題上次修改日期：** 2012年-10-09_</span><span class="sxs-lookup"><span data-stu-id="e8a3e-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="e8a3e-104">一般而言，Lync Server 2010 通訊錄會移轉，以及您的拓樸的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="e8a3e-105">不過，您可能需要執行一些步驟，移轉後，如果您在 Lync Server 2010 環境中自訂下列：</span><span class="sxs-lookup"><span data-stu-id="e8a3e-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="e8a3e-106">將**PartitionbyOU** WMI 屬性設為通訊錄項目分組依組織單位 (OU)。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="e8a3e-107">自訂通訊錄正規化規則。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="e8a3e-108">變更**將 UseNormalizationRules**參數的預設值為 False。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="e8a3e-109">**分組的通訊錄項目**</span><span class="sxs-lookup"><span data-stu-id="e8a3e-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="e8a3e-110">如果您將**PartitionbyOU** WMI 屬性設定為 True，針對每個 OU 建立通訊錄時，您需要的使用者和連絡人上設定**Msrtcsip-groupingid** Active Directory 屬性，如果您想要繼續進行分組通訊錄項目。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="e8a3e-111">您可能想要限制的 Address Book 搜尋範圍的群組通訊錄項目。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="e8a3e-112">若要使用**Msrtcsip-groupingid**屬性，撰寫指令碼，以填入屬性，將指派的相同值的所有使用者想要群組在一起。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="e8a3e-113">例如，指派為 OU 中的所有使用者的單一值。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="e8a3e-114">**通訊錄正規化規則**</span><span class="sxs-lookup"><span data-stu-id="e8a3e-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="e8a3e-115">如果您在 Lync Server 2010 環境中自訂通訊錄正規化規則，您必須將自訂的規則移轉至試驗集區。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="e8a3e-116">如果您不沒有自訂通訊錄正規化規則，您必須將移轉的通訊錄服務則是 nothing。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="e8a3e-117">Lync Server 2013 的預設正規化規則會與預設的 Lync Server 2010 規則相同。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="e8a3e-118">遵循本節稍後將自訂的正規化規則的程序。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e8a3e-119">如果您的組織使用遠端呼叫控制，且您自訂通訊錄正規化規則，您必須執行此程序，本主題中後，您可以使用遠端呼叫控制即可。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="e8a3e-120">程序需要相等的權限或 RTCUniversalServerAdmins 群組的成員資格。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="e8a3e-121">**UseNormalizationRules 設為 False**</span><span class="sxs-lookup"><span data-stu-id="e8a3e-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="e8a3e-122">如果您將值**usenormalizationrules**設為 False，讓使用者可以使用電話號碼，而不需套用正規化規則的 Lync Server 2013 所定義的 Active Directory 網域服務中，您需要將**UseNormalizationRules**和**IgnoreGenericRules**參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="e8a3e-123">遵循本節稍後將這些參數設定為 True 的程序。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="e8a3e-124">移轉通訊錄自訂正規化規則</span><span class="sxs-lookup"><span data-stu-id="e8a3e-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="e8a3e-125">尋找公司\_電話\_號碼\_正規化\_Rules.txt 檔案通訊錄共用資料夾的根目錄中，並將它複製到 Lync Server 2013 試驗集區中通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e8a3e-126">範例通訊錄正規化規則已安裝在您 ABS Web 元件的檔案目錄中。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="e8a3e-127">路徑是<STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013\Web Components\Address 通訊錄 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt，</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="e8a3e-128">要複製此檔案，然後重新命名為&nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;至通訊錄共用的資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="e8a3e-129">例如，通訊錄共用<STRONG>$serverX</STRONG>，&nbsp;路徑會類似： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="e8a3e-130">使用文字編輯器，例如 「 記事本 」，若要開啟 [公司\_電話\_號碼\_正規化\_Rules.txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="e8a3e-131">Lync Server 2013 中，某些類型的項目將無法正確運作。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="e8a3e-132">查看的這個步驟中所述的項目類型的檔案，視需要編輯這些，將變更儲存至試驗集區中通訊錄共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="e8a3e-133">包含必要的空白字元或標點符號原因正規化規則失敗，因為這些字元會移除超出輸入正規化規則的字串的字串。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="e8a3e-134">如果您有包含必要的空白字元或標點符號的字串，您要修改的字串。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="e8a3e-135">例如，下列字串會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="e8a3e-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="e8a3e-136">下列字串將不會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="e8a3e-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="e8a3e-137">將 UseNormalizationRules 和 IgnoreGenericRules 設為 true</span><span class="sxs-lookup"><span data-stu-id="e8a3e-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="e8a3e-138">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="e8a3e-139">執行下列其中一項動作：</span><span class="sxs-lookup"><span data-stu-id="e8a3e-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="e8a3e-140">如果您的部署包含 Lync Server 2013，請在全域層級**UseNormalizationRules**和**IgnoreGenericRules**的值變更為 True 執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e8a3e-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="e8a3e-141">如果您的部署包含 Lync Server 2013 和 Lync Server 2010 或 Office Communications Server 2007 R2 的組合，請執行下列 cmdlet，並將其指派給拓撲中每個 Lync Server 2013 集區：</span><span class="sxs-lookup"><span data-stu-id="e8a3e-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="e8a3e-142">等待所有集區上發生的中央管理存放區複寫。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="e8a3e-143">修改電話正規化規則檔案中，「 公司\_電話\_號碼\_正規化\_Rules.txt 」，若要清除的內容部署。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="e8a3e-144">檔案是在每個 Lync Server 2013 集區的檔案共用上。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="e8a3e-145">如果檔案不存在，然後建立空的檔案，名為 「 公司\_電話\_號碼\_正規化\_Rules.txt 」。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="e8a3e-146">請稍候幾分鐘的所有前端集區讀取新檔案。</span><span class="sxs-lookup"><span data-stu-id="e8a3e-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="e8a3e-147">在部署中的每個 Lync Server 2013 集區上執行下列 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="e8a3e-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

