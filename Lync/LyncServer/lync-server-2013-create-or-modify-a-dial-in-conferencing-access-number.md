---
title: Lync Server 2013：建立或修改電話撥入式會議存取號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a dial-in conferencing access number
ms:assetid: 06f55c28-57f8-4d4e-8313-9740846796d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398126(v=OCS.15)
ms:contentKeyID: 48183304
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7ecfebba25d45f53633fdd425e5901929fc32d0c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758077"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改電話撥入式會議存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

如果您想要建立或修改電話撥入式會議存取號碼，請遵循下列步驟。

<div>


> [!IMPORTANT]  
> 在您建立新的撥入存取號碼之前，您必須在與新的撥入存取號碼相關聯的撥號方案中設定電話撥入式會議區域。 多個撥號方案可以使用同一個區域。



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>建立或修改撥入存取號碼

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [**撥入存取號碼**]。

4.  在 [**撥入存取號碼**] 頁面上，執行下列其中一項操作：
    
      - 按一下 [**新增**] 以開啟**新的撥入存取號碼**。
    
      - 按一下清單中的其中一個撥入存取號碼，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。
        
        <div>
        

        > [!NOTE]  
        > 使用 [搜尋] 欄位來搜尋撥入存取號碼清單中的欄內容，可能不會產生您預期的結果。 您可以改為依您想要查看或變更的撥入存取號碼來排序清單。

        
        </div>

5.  在 [**顯示號碼**] 中，輸入「公用交換電話網絡（PSTN）電話撥打電話給」加入會議的電話號碼。
    
    <div>
    

    > [!NOTE]  
    > 這個數位會顯示在 [會議邀請] 和 [電話撥入式會議設定] 網頁上。

    
    </div>

6.  在 [**顯示名稱**] 中，輸入撥入存取號碼的描述。 這是與 Lync 搜尋結果中的撥入存取號碼相關聯的名稱。
    
    <div>
    

    > [!NOTE]  
    > 當使用者呼叫存取號碼時，此名稱就會顯示在用戶端中。

    
    </div>

7.  在 [**行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 E. 164 個數字，包括數位前面的 + 符號，不含空格。 例如，電話： + 14255550200。
    
    <div>
    

    > [!NOTE]  
    > 其他電話撥入式會議存取號碼無法重複使用相同的行 URI。

    
    </div>

8.  在**SIP URI**中，請執行下列動作：
    
      - 在文字方塊中，輸入此電話撥入式會議存取號碼的唯一 SIP URI。 此 SIP URI 會顯示在各種位置，包括但不限於呼叫通知訊息及舊版 Communicator 用戶端版本。
        
        <div>
        

        > [!NOTE]  
        > 其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。 在建立存取號碼之後，便無法修改 SIP URI。 變更 SIP URI 的唯一方式是刪除並重新建立存取號碼。

        
        </div>
    
      - 在下拉式清單方塊中，按一下支援此撥入存取號碼之會議助理應用程式的網域。

9.  在 [Pool] （**池**）中，按一下執行支援此撥入存取號碼之會議助理實例的池。
    
    <div>
    

    > [!NOTE]  
    > 如果您在建立存取號碼後需要變更池，您必須使用<STRONG>CsApplicationEndpoint</STRONG> Cmdlet，或刪除並重新建立存取號碼。

    
    </div>

10. 在**主要語言**中，按一下針對此撥入存取號碼播放提示的語言。
    
    <div>
    

    > [!NOTE]  
    > 主要語言是會議助理用來接聽通話的語言。 支援的語言會顯示在電話撥入式會議設定網頁上的每個存取電話號碼旁邊。

    
    </div>

11. 可選在**次要語言（最多四個）** 中，按一下 [**新增**]，選取您想要支援來電者至此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 您最多可以為每個撥入存取號碼選擇四個次要語言。 使用者在撥入會議時，輸入會議 ID 前，就可以選取次要語言。

    
    </div>

12. 若要新增撥入存取號碼的地區，請在 [**相關區域**] 底下，按一下 [**新增**]，按一下與此撥入存取號碼的撥號方案相關聯的一個或多個區域，然後按一下 **[確定]**。

13. 若要從撥入存取號碼刪除區域，請在 [**相關區域**] 底下，按一下您要刪除的區域，然後按一下 [**移除**]。

14. 按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

