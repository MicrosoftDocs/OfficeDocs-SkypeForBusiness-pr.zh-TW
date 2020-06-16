---
title: 將多個使用者移至試驗集區
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c663566605529b25d9890bb31cba462364c813
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>將多個使用者移至試驗集區

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-02_

您可以使用 Lync Server 2013 控制台或 Lync Server 2013 管理命令介面，將多個使用者從 Office 通訊伺服器 2007 R2 集區移至 Lync Server 2013 試驗集區。

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>使用 Lync Server 2013 控制台移動多位使用者

1.  開啟 [ **Lync Server 控制台**]。

2.  從 [使用者搜尋]**** 索引標籤，按一下 [搜尋]**** 按鈕。

3.  接著，按一下 [新增篩選]****。

4.  建立篩選，其中的 [Office Communications Server 使用者]**** 等於 [True]****。

5.  按一下 [**尋找**] 搜尋舊版 Office 通訊伺服器 2007 R2 使用者。

6.  選取兩個要移至 Lync Server 2013 集區的使用者。 在此範例中，我們會將使用者移 Chen 陽和聖誕老人聖誕 Hansen。
    
    ![從搜尋 OCS 使用者顯示的使用者清單](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "從搜尋 OCS 使用者顯示的使用者清單")  

7.  從 [**動作**] 功能表中，選取 [**將選取的使用者移至集**區]。

8.  從下拉式清單中，選取 [Lync Server 2013 集區]。

9.  按一下 [動作]****，然後按一下 [將選取的使用者移至集區]****。 按一下 [確定]。
    
    ![移動使用者、目的地註冊集區] 對話方塊](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "移動使用者、目的地註冊集區] 對話方塊")  

10. 確認使用者的 [**報名者集**區] 欄現在包含 Lync Server 2013 集區，這表示使用者已順利移動。

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面移動多位使用者

1.  開啟 [Lync Server 2013 管理命令介面]。

2.  在命令列上輸入下列命令，並將**User1**和使用者2取代為您想要移動的特定使用者名稱，並將**集區 \_ FQDN** **取代為目的地**集區的名稱。 在此範例中，我們會移動使用者 Hao Chen 和 Katie 約旦。
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![移動舊版使用者的範例 Cmdlet](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "移動舊版使用者的範例 Cmdlet")  

3.  在命令列上輸入下列命令
    
        Get-CsUser -Identity "User1"

4.  **註冊機構集**區的身分識別現在應該指向您在上一個步驟中指定為**集區 \_ FQDN**的集區。 這個身分識別的出現表示已成功移動使用者。 重複步驟**以驗證使用者2是否已移動**。
    
    ![PowerShell Get-UsUser 識別指令程式的輸出](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "PowerShell Get-UsUser 識別指令程式的輸出")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>使用 Lync Server 2013 管理命令介面同時移動所有使用者

在此範例中，所有使用者都已傳回 Office 通訊伺服器 2007 R2 集區（pool01.contoso.net）。 使用 Lync Server 2013 管理命令介面時，我們會同時將所有使用者同時移至 Lync Server 2013 集區（pool02.contoso.net）。

1.  開啟 [ **Lync Server 2013 管理命令**介面]。

2.  在命令列輸入下列命令：
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![移動集區中所有舊版使用者的範例 Cmdlet](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "移動集區中所有舊版使用者的範例 Cmdlet")  

3.  接下來，針對其中一位試驗使用者執行**Get-CsUser** 。
    
        Get-CsUser -Identity "Hao Chen"

4.  每個使用者的**註冊區集**區身分識別，都指向您 \_ 在上一個步驟中指定為「集區 FQDN」的集區。 這個身分識別的出現表示已成功移動使用者。

5.  此外，我們可以在 Lync Server 2013 控制台中查看使用者清單，並確認 [註冊機集區] 值現在是否指向 Lync Server 2013 集區。
    
    ![Lync Server 2013 控制台使用者清單](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Lync Server 2013 控制台使用者清單")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

