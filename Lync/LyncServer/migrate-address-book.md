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
ms.openlocfilehash: b678dea3e8ad7f05f82d28dfdd23ad9e45b38e92
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765281"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="dec72-102">移轉通訊錄</span><span class="sxs-lookup"><span data-stu-id="dec72-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dec72-103">_**主題上次修改日期：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="dec72-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="dec72-104">一般來說，Lync Server 2010 通訊錄會與其他拓撲一起遷移。</span><span class="sxs-lookup"><span data-stu-id="dec72-104">In general, the Lync Server 2010 Address Book is migrated along with the rest of your topology.</span></span> <span data-ttu-id="dec72-105">不過，如果您在 Lync Server 2010 環境中自訂下列專案，可能需要執行一些遷移後步驟：</span><span class="sxs-lookup"><span data-stu-id="dec72-105">However, you might need to perform some post-migration steps if you customized the following in your Lync Server 2010 environment:</span></span>

  - <span data-ttu-id="dec72-106">將 [ **PartitionbyOU** WMI] 屬性設定為 [依組織單位（OU）群組通訊錄專案]。</span><span class="sxs-lookup"><span data-stu-id="dec72-106">Set the **PartitionbyOU** WMI property to group Address Book entries by organizational unit (OU).</span></span>

  - <span data-ttu-id="dec72-107">已自訂通訊錄正常化規則。</span><span class="sxs-lookup"><span data-stu-id="dec72-107">Customized the Address Book normalization rules.</span></span>

  - <span data-ttu-id="dec72-108">已將**UseNormalizationRules**參數的預設值變更為 False。</span><span class="sxs-lookup"><span data-stu-id="dec72-108">Changed the default value for the **UseNormalizationRules** parameter to False.</span></span>

<span data-ttu-id="dec72-109">**群組通訊錄專案**</span><span class="sxs-lookup"><span data-stu-id="dec72-109">**Grouped Address Book Entries**</span></span>

<span data-ttu-id="dec72-110">如果您將**PartitionbyOU** WMI 屬性設定為 True，為每個 OU 建立通訊錄，您必須在使用者和連絡人上設定**msRTCSIP-GroupingId** Active Directory 屬性，才能繼續群組通訊錄專案。</span><span class="sxs-lookup"><span data-stu-id="dec72-110">If you set the **PartitionbyOU** WMI property to True to create address books for each OU, you need to set the **msRTCSIP-GroupingId** Active Directory attribute on users and contacts if you want to continue grouping address book entries.</span></span> <span data-ttu-id="dec72-111">您可能會想要將通訊錄專案分組，以限制通訊錄搜尋的範圍。</span><span class="sxs-lookup"><span data-stu-id="dec72-111">You might want to group address book entries to limit the scope of Address Book searches.</span></span> <span data-ttu-id="dec72-112">若要使用**msRTCSIP-GroupingId**屬性，請撰寫腳本來填入屬性，並為您要組成群組的所有使用者指派相同的值。</span><span class="sxs-lookup"><span data-stu-id="dec72-112">To use the **msRTCSIP-GroupingId** attribute, write a script to populate the attribute, assigning the same value for all of the users that you want to group together.</span></span> <span data-ttu-id="dec72-113">例如，為 OU 中的所有使用者指派單一值。</span><span class="sxs-lookup"><span data-stu-id="dec72-113">For example, assign a single value for all the users in an OU.</span></span>

<span data-ttu-id="dec72-114">**通訊錄正常化規則**</span><span class="sxs-lookup"><span data-stu-id="dec72-114">**Address Book Normalization Rules**</span></span>

<span data-ttu-id="dec72-115">如果您在 Lync Server 2010 環境中自訂通訊錄正常化規則，則必須將自訂規則遷移至您的試驗區。</span><span class="sxs-lookup"><span data-stu-id="dec72-115">If you customized Address Book normalization rules in your Lync Server 2010 environment, you must migrate the customized rules to your pilot pool.</span></span> <span data-ttu-id="dec72-116">如果您沒有自訂通訊錄正常化規則，您就無法針對通訊錄服務進行任何遷移。</span><span class="sxs-lookup"><span data-stu-id="dec72-116">If you did not customize Address Book normalization rules, you have nothing to migrate for Address Book service.</span></span> <span data-ttu-id="dec72-117">Lync Server 2013 的預設正常化規則與 Lync Server 2010 的預設規則相同。</span><span class="sxs-lookup"><span data-stu-id="dec72-117">The default normalization rules for Lync Server 2013 are the same as the default rules for Lync Server 2010.</span></span> <span data-ttu-id="dec72-118">遵循本節稍後的程式，以遷移自訂的正常化規則。</span><span class="sxs-lookup"><span data-stu-id="dec72-118">Follow the procedure later in this section to migrate customized normalization rules.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dec72-119">如果您的組織使用遠端通話控制，且您已自訂通訊錄正常化規則，您必須先執行本主題中的程式，才能使用遠端通話控制。</span><span class="sxs-lookup"><span data-stu-id="dec72-119">If your organization uses remote call control and you customized Address Book normalization rules, you must perform the procedure in this topic before you can use remote call control.</span></span> <span data-ttu-id="dec72-120">程式需要 RTCUniversalServerAdmins 群組或對等許可權的成員資格。</span><span class="sxs-lookup"><span data-stu-id="dec72-120">The procedure requires membership in the RTCUniversalServerAdmins group or equivalent rights.</span></span>



</div>

<span data-ttu-id="dec72-121">**UseNormalizationRules 設為 False**</span><span class="sxs-lookup"><span data-stu-id="dec72-121">**UseNormalizationRules Set to False**</span></span>

<span data-ttu-id="dec72-122">如果您將**UseNormalizationRules**的值設為 False，讓使用者可以在 Active Directory 網域服務中定義的電話號碼，而不需讓 Lync Server 2013 套用正常化規則，您必須將**UseNormalizationRules**和**IgnoreGenericRules**參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="dec72-122">If you set the value for **UseNormalizationRules** to False so that users can use phone numbers as they are defined in Active Directory Domain Services without having Lync Server 2013 apply normalization rules, you need to set the **UseNormalizationRules** and **IgnoreGenericRules** parameters to True.</span></span> <span data-ttu-id="dec72-123">遵循本節稍後的程式，將這些參數設定為 True。</span><span class="sxs-lookup"><span data-stu-id="dec72-123">Follow the procedure later in this section to set these parameters to True.</span></span>

<div>

## <a name="to-migrate-address-book-customized-normalization-rules"></a><span data-ttu-id="dec72-124">遷移通訊錄自訂的正常化規則</span><span class="sxs-lookup"><span data-stu-id="dec72-124">To migrate Address Book customized normalization rules</span></span>

1.  <span data-ttu-id="dec72-125">尋找通訊錄\_共用\_資料夾\_根目錄\_中的公司電話號碼正規化規則 .Txt 檔案，並將其複製到 Lync Server 2013 試驗區中通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="dec72-125">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="dec72-126">範例通訊錄正常化規則已經安裝在您的 ABS 網頁元件檔案目錄中。</span><span class="sxs-lookup"><span data-stu-id="dec72-126">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="dec72-127">路徑是<STRONG>$installedDriveLetter： \Program Files\Microsoft Lync Server 2013 \ Web Components\Address 書籍 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt、</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dec72-127">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="dec72-128">您可以將此檔案複製並重新&nbsp;命名為<STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;為通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="dec72-128">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="dec72-129">例如，在<STRONG>$serverX</STRONG>中共用通訊錄，&nbsp;路徑會類似： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="dec72-129">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="dec72-130">使用文字編輯器（例如記事本）來開啟\_公司電話\_號碼\_正常化\_規則 .txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="dec72-130">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="dec72-131">在 Lync Server 2013 中，某些類型的專案將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="dec72-131">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="dec72-132">在檔案中查看此步驟中描述的專案類型，視需要進行編輯，然後將變更儲存到您的試驗區中的通訊錄共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="dec72-132">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="dec72-133">包含所需空格或標點符號的字串會導致正常化規則失敗，因為這些字元會從輸入到正常化規則的字串中去除。</span><span class="sxs-lookup"><span data-stu-id="dec72-133">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="dec72-134">如果您有包含所需空格或標點符號的字串，您必須修改字串。</span><span class="sxs-lookup"><span data-stu-id="dec72-134">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="dec72-135">例如，下列字串將導致正常化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="dec72-135">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="dec72-136">下列字串不會導致正常化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="dec72-136">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<div>

## <a name="to-set-usenormalizationrules-and-ignoregenericrules-to-true"></a><span data-ttu-id="dec72-137">若要將 UseNormalizationRules 和 IgnoreGenericRules 設定為 true</span><span class="sxs-lookup"><span data-stu-id="dec72-137">To set UseNormalizationRules and IgnoreGenericRules to true</span></span>

1.  <span data-ttu-id="dec72-138">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="dec72-138">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="dec72-139">請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="dec72-139">Do one of the following:</span></span>
    
      - <span data-ttu-id="dec72-140">如果您的部署只包含 Lync Server 2013，請在全域層級執行下列 Cmdlet，將**UseNormalizationRules**和**IgnoreGenericRules**的值變更為 True：</span><span class="sxs-lookup"><span data-stu-id="dec72-140">If your deployment includes only Lync Server 2013, run the following cmdlet at the global level to change the values for **UseNormalizationRules** and **IgnoreGenericRules** to True:</span></span>
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - <span data-ttu-id="dec72-141">如果您的部署包括 Lync Server 2013 和 Lync Server 2010 或 Office 通訊伺服器 2007 R2 的組合，請執行下列 Cmdlet，並將它指派給拓撲中的每個 Lync Server 2013 池：</span><span class="sxs-lookup"><span data-stu-id="dec72-141">If your deployment includes a combination of Lync Server 2013 and Lync Server 2010 or Office Communications Server 2007 R2, run the following cmdlet and assign it to each Lync Server 2013 pool in the topology:</span></span>
        
            New-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  <span data-ttu-id="dec72-142">等到中央管理儲存區複製在所有的池中進行。</span><span class="sxs-lookup"><span data-stu-id="dec72-142">Wait for Central Management store replication to occur on all pools.</span></span>

4.  <span data-ttu-id="dec72-143">針對您的部署，修改手機正常化規則\_檔案\_"\_公司\_電話號碼正規化規則 .txt"，以清除內容。</span><span class="sxs-lookup"><span data-stu-id="dec72-143">Modify the phone normalization rules file, "Company\_Phone\_Number\_Normalization\_Rules.txt", for your deployment to clear the content.</span></span> <span data-ttu-id="dec72-144">檔案位於每個 Lync Server 2013 池的檔案共用位置。</span><span class="sxs-lookup"><span data-stu-id="dec72-144">The file is on the file share of each Lync Server 2013 pool.</span></span> <span data-ttu-id="dec72-145">如果檔案不存在，請建立名為「\_公司電話\_號碼\_正常化\_Rules .txt」的空檔案。</span><span class="sxs-lookup"><span data-stu-id="dec72-145">If the file is not present, then create an empty file named "Company\_Phone\_Number\_Normalization\_Rules.txt".</span></span>

5.  <span data-ttu-id="dec72-146">針對所有前端池，請等候幾分鐘，以讀取新檔案。</span><span class="sxs-lookup"><span data-stu-id="dec72-146">Wait several minutes for all Front End pools to read the new files.</span></span>

6.  <span data-ttu-id="dec72-147">在部署的每個 Lync Server 2013 池中執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dec72-147">Run the following cmdlet on each Lync Server 2013 pool in your deployment:</span></span>
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

