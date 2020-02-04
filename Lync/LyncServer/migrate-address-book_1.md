---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c904a122f781da08c92c6b1123cfeb1944dd2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="c1cbb-102">移轉通訊錄</span><span class="sxs-lookup"><span data-stu-id="c1cbb-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c1cbb-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c1cbb-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c1cbb-104">**遷移通訊錄自訂的正常化規則**</span><span class="sxs-lookup"><span data-stu-id="c1cbb-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="c1cbb-105">尋找通訊錄\_共用\_資料夾\_根目錄\_中的公司電話號碼正規化規則 .Txt 檔案，並將其複製到 Lync Server 2013 試驗區中通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c1cbb-106">範例通訊錄正常化規則已經安裝在您的 ABS 網頁元件檔案目錄中。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="c1cbb-107">路徑是<STRONG>$installedDriveLetter： \Program Files\Microsoft Lync Server 2013 \ Web Components\Address 書籍 Files\Files\ Sample_Company_Phone_Number_Normalization_Rules .txt、</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="c1cbb-108">您可以將此檔案複製並重新&nbsp;命名為<STRONG>Company_Phone_Number_Normalization_Rules</STRONG> &nbsp;為通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="c1cbb-109">例如，在<STRONG>$serverX</STRONG>中共用通訊錄，&nbsp;路徑會類似： <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="c1cbb-110">使用文字編輯器（例如記事本）來開啟\_公司電話\_號碼\_正常化\_規則 .txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="c1cbb-111">在 Lync Server 2013 中，某些類型的專案將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="c1cbb-112">在檔案中查看此步驟中描述的專案類型，視需要進行編輯，然後將變更儲存到您的試驗區中的通訊錄共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="c1cbb-113">包含所需空格或標點符號的字串會導致正常化規則失敗，因為這些字元會從輸入到正常化規則的字串中去除。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="c1cbb-114">如果您有包含所需空格或標點符號的字串，您必須修改字串。</span><span class="sxs-lookup"><span data-stu-id="c1cbb-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="c1cbb-115">例如，下列字串將導致正常化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="c1cbb-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="c1cbb-116">下列字串不會導致正常化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="c1cbb-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

