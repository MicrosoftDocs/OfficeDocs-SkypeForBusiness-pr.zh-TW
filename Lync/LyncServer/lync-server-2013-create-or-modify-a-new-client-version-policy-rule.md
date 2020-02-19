---
title: Lync Server 2013： 建立或修改新的用戶端版本原則規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9207ff9d615990d0e944ac8c435561f0c937f089
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>建立或修改 Lync Server 2013 中新的用戶端版本原則規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-01-21_

用戶端版本原則規則定義當使用者嘗試登入特定的用戶端與用戶端版本時應該採取的動作。 您可以建立或修改 Lync Server 2013 控制台從用戶端版本原則的個別規則。

<div>


> [!IMPORTANT]  
> 規則會列在的優先順序。 比方說，如果您有一個規則，可讓用戶端執行連線 1.5 版，後面接著會封鎖用戶端規則執行更早版本的版本比 2.0 中，第一個規則的優先順序，和允許執行 1.5 版用戶端連接。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>若要建立或修改用戶端版本原則規則與 Lync Server Control Panel

1.  [建立或修改 Lync Server 2013 中的新用戶端版本原則](lync-server-2013-create-or-modify-a-new-client-version-policy.md)與 Lync Server Control Panel。

2.  在 [**編輯用戶端版本原則**] 頁面上，執行下列其中一項：
    
      - 按一下 [**新增**]，以建立新的用戶端版本規則。
    
      - 按一下其中一個已定義的用戶端類型的清單中，，然後按一下 [**顯示詳細資料**。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用萬用字元表示用戶端類型。

    
    </div>

3.  **使用者代理程式**] 中選取的用戶端類型。

4.  [**版本號碼**] 下方執行下列動作：
    
      - 在 [**主要版本**中，輸入對應至用戶端主要版本號碼。
    
      - 在 [**次要版本**中，輸入對應至用戶端次要版本號碼。
    
      - 在**建立**時，輸入對應至用戶端主要和次要版本號碼。
    
      - 在**更新**時，輸入對應至用戶端更新版本的號碼。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用萬用字元表示用戶端版本號碼。

    
    </div>

5.  若要指定您在先前步驟中，在**比較作業**中，指定用戶端版本比對作業按一下下列其中一項：
    
      - **相同**
    
      - **不相同**
    
      - **新於**
    
      - **新於或相同**
    
      - **舊於**
    
      - **舊於或相同**

6.  若要指定的巨集指令來執行前述步驟中的條件符合時，按一下 [**巨集指令**中下列其中之一：
    
      - 若要允許用戶端登入，請按一下 [**允許**]。
    
      - 若要允許用戶端登入，並從 Windows Server Update Service 或 Microsoft Update 」 接收更新，請按一下 [**允許並升級**。 選取 [使用者代理程式**OC**時才使用此巨集指令。
        
        <div>
        

        > [!NOTE]  
        > 選取此巨集指令會顯示 [下一次使用者登入 Lync 2013 的通知。 通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。 若要避免混淆，您應該僅在更新可用時選擇此動作。

        
        </div>
    
      - 若要允許用戶端登入並顯示一則訊息關於到哪裡下載另一個用戶端版本，請按一下 [**以 URL 允許**]。 您稍後在此程序中指定的 URL。
    
      - 若要防止用戶端登入，請按一下 [**封鎖**]。
    
      - 若要防止用戶端登入，並允許用戶端以從 Windows Server Update Service 或 Microsoft Update 」 接收更新，請按一下 [**封鎖並升級**。 選取 [使用者代理程式**OC**時才使用此巨集指令。
    
      - 若要防止用戶端登入並顯示一則訊息關於到哪裡下載另一個用戶端版本，按一下 [**以 URL 封鎖**]。 您稍後在此程序中指定的 URL。

7.  （選用）如果您在先前步驟中，按一下**以 URL 允許**] 或 [**以 URL 封鎖**]，類型用戶端下載**URL**] 中的訊息中包含的 URL。

8.  按一下 [**確定**]，然後按一下 [**認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

