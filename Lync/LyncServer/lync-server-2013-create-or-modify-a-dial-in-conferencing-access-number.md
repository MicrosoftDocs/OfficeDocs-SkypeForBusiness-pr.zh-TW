---
title: Lync Server 2013：建立或修改電話撥入式會議存取號碼
description: Lync Server 2013：建立或修改電話撥入式會議存取號碼。
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
ms.openlocfilehash: 187361ab839fe2f80fda7cb68285c8f36398f5a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577959"
---
# <a name="create-or-modify-a-dial-in-conferencing-access-number-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改電話撥入式會議存取號碼

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

如果您想建立或修改電話撥入式會議存取號碼，請遵循下列步驟。

<div>


> [!IMPORTANT]  
> 您必須先在與新的撥入存取號碼關聯的撥號對應表中設定電話撥入式會議區域，才可建立新的撥入存取號碼。多個撥號對應表可使用相同的區域。



</div>

<div>

## <a name="to-create-or-modify-a-dial-in-access-number"></a>若要建立或修改撥入存取號碼

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[會議]**，然後按一下 **[撥入存取號碼]**。

4.  在 **[撥入存取號碼]** 頁面中，執行下列其中一項：
    
      - 按一下 **[新增]** 以開啟 **[新增撥入存取號碼]**。
    
      - 按一下清單中的其中一個撥入存取號碼，按一下 **[編輯]**，然後按一下 **[顯示詳細資料]**。
        
        <div>
        

        > [!NOTE]  
        > 使用搜尋欄位來搜尋撥入存取號碼清單中可能無法產生預期結果的欄內容。請依照您想要的欄排序此清單，找出您想檢視或變更的撥入存取號碼。

        
        </div>

5.  在 [ **顯示號碼**] 中，輸入公用交換電話網路 (PSTN) 電話使用者撥號以加入會議的電話號碼。
    
    <div>
    

    > [!NOTE]  
    > 此號碼會顯示在會議邀請中和電話撥入式會議設定網頁上。

    
    </div>

6.  在 [ **顯示名稱**] 中，輸入撥入存取號碼的描述。 這是與 Lync 搜尋結果中的撥入存取號碼相關聯的名稱。
    
    <div>
    

    > [!NOTE]  
    > 當使用者呼叫存取號碼時，此名稱會顯示在用戶端中。

    
    </div>

7.  在 [ **行 uri**] 中，輸入電話 uri 格式的撥入存取號碼的 e.164 號碼，包含號碼前面的 + 符號，並排除空格。 例如電話： + 14255550200。
    
    <div>
    

    > [!NOTE]  
    > 其他電話撥入式會議存取號碼無法重複使用相同的列 URI。

    
    </div>

8.  在 [ **SIP URI**] 中，執行下列動作：
    
      - 在文字方塊中，輸入此撥入式會議存取號碼的唯一 SIP URI。 這種 SIP URI 會顯示在不同的位置，包括（但不限於）來電通知訊息和舊版的 Communicator 用戶端。
        
        <div>
        

        > [!NOTE]  
        > 其他電話撥入式會議存取號碼無法重複使用相同的 SIP URI。 建立存取號碼之後，便無法修改 SIP URI。 變更 SIP URI 的唯一方法是刪除並重新建立存取號碼。

        
        </div>
    
      - 在下拉式清單方塊中，按一下支援此撥入存取號碼之會議應答應用程式的網域。

9.  在 [ **集**區] 中，按一下執行支援此撥入存取號碼之會議助理實例的集區。
    
    <div>
    

    > [!NOTE]  
    > 如果您在建立存取號碼之後需要變更集區，則必須使用 <STRONG>Move-CsApplicationEndpoint</STRONG> Cmdlet，或刪除並重新建立存取號碼。

    
    </div>

10. 在 [ **主要語言**] 中，按一下為此撥入存取號碼播放提示時所使用的語言。
    
    <div>
    

    > [!NOTE]  
    > 主要語言是會議助理用來接聽通話的語言。 在 [電話撥入式會議設定] 網頁上的每一個存取電話號碼旁會顯示支援的語言。

    
    </div>

11.  (選用) 在 **次要語言中 (最多四個) **，請按一下 [ **新增**]，選取您要支援的來電者撥打此撥入存取號碼的一或多個其他語言，然後按一下 **[確定]**。
    
    <div>
    

    > [!NOTE]  
    > 您最多可以為每個撥入存取號碼選擇四種次要語言。 使用者在撥入會議時，可以先選取次要語言，再進入會議識別碼。

    
    </div>

12. 若要新增撥入存取號碼的地區，請在 [ **關聯的地區**] 下，按一下 [ **新增**]，然後按一下與此撥入存取號碼的撥號對應表相關聯的一個或多個地區，然後按一下 **[確定]**。

13. 若要從撥入存取號碼中刪除地區，請在 [ **關聯的地區**] 下，按一下您要刪除的地區，然後按一下 [ **移除**]。

14. 按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

