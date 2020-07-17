---
title: 移轉通訊錄
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 937bf9dfff07591ea12a2c78604ab82fa34e97f6
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757024"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="107f4-102">移轉通訊錄</span><span class="sxs-lookup"><span data-stu-id="107f4-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="107f4-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="107f4-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="107f4-104">**遷移通訊錄自訂正常化規則**</span><span class="sxs-lookup"><span data-stu-id="107f4-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="107f4-105">\_ \_ \_ \_ 在 [通訊錄] 共用資料夾的根目錄中尋找公司電話號碼正規化Rules.txt 檔案，並將它複製到 Lync Server 2013 試驗集區中的 [通訊錄共用資料夾] 根。</span><span class="sxs-lookup"><span data-stu-id="107f4-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="107f4-106">您的 ABS 網頁元件檔案目錄中已安裝範例通訊錄正常化規則。</span><span class="sxs-lookup"><span data-stu-id="107f4-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="107f4-107">路徑為<STRONG>$installedDriveLetter： \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt，</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="107f4-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="107f4-108">您可以將此檔案複製並重新命名為 &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp; 通訊錄共用資料夾的根目錄。</span><span class="sxs-lookup"><span data-stu-id="107f4-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="107f4-109">例如， <STRONG>$serverX</STRONG>中共用的通訊錄， &nbsp; 該路徑會類似如下： <STRONG> \\ $serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="107f4-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="107f4-110">使用文字編輯器（例如 [記事本]）開啟公司 \_ 電話號碼正規化 \_ \_Rules.txt 檔 \_ 。</span><span class="sxs-lookup"><span data-stu-id="107f4-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="107f4-111">在 Lync Server 2013 中某些類型的專案將無法正確運作。</span><span class="sxs-lookup"><span data-stu-id="107f4-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="107f4-112">查看此步驟中所述之專案類型的檔案，視需要進行編輯，然後將變更儲存至試驗集區中的通訊錄共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="107f4-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="107f4-113">包含必要空格或標點符號的字串會導致正規化規則失敗，因為這些字元會從輸入到正規化規則的字串中去掉。</span><span class="sxs-lookup"><span data-stu-id="107f4-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="107f4-114">如果您有包含必要空格或標點符號的字串，您必須修改字串。</span><span class="sxs-lookup"><span data-stu-id="107f4-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="107f4-115">例如，下列字串會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="107f4-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="107f4-116">下列字串將不會導致正規化規則失敗：</span><span class="sxs-lookup"><span data-stu-id="107f4-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

