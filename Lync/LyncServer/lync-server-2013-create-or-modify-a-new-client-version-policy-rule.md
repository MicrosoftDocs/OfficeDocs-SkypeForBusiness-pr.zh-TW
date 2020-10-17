---
title: Lync Server 2013：建立或修改新的用戶端版本原則規則
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
ms.openlocfilehash: 732113537b79ad2ac767f64b861f296be508899c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512720"
---
# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改新的用戶端版本原則規則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-21_

用戶端版本原則規則定義當使用者嘗試以特定用戶端和用戶端版本登入時應該採取的動作。 您可以從 Lync Server 2013 控制台建立或修改用戶端版本原則的個別規則。

<div>


> [!IMPORTANT]  
> 規則會依優先權順序列出。 例如，如果您有允許執行版本1.5 之用戶端進行連線的規則，接著會封鎖執行高於2.0 之版本之用戶端的規則，第一個規則優先，而且執行版本1.5 的用戶端可以進行連線。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>使用 Lync Server 控制台建立或修改用戶端版本原則規則

1.  使用 Lync Server 控制台，[在 Lync server 2013 中建立或修改新的用戶端版本原則](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。

2.  在 [ **編輯用戶端版本原則** ] 頁面上，執行下列其中一項操作：
    
      - 按一下 [ **新增** ] 建立新的用戶端版本規則。
    
      - 按一下清單中已定義的其中一個用戶端類型，然後按一下 [ **顯示詳細資料**]。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用萬用字元來表示用戶端類型。

    
    </div>

3.  在 [ **使用者代理程式**] 中，選取用戶端類型。

4.  在 [ **版本編號**] 底下，執行下列動作：
    
      - 在 [ **主要版本**] 中，輸入對應至用戶端主要版本的號碼。
    
      - 在 [ **次要版本**] 中，輸入對應至用戶端次要版本的號碼。
    
      - 在 [ **組建**] 中，輸入對應至用戶端主要和次要版本的號碼。
    
      - 在 [ **更新**] 中，輸入對應至用戶端更新版本的號碼。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用萬用字元表示用戶端版本號碼。

    
    </div>

5.  若要為您在上述步驟中指定的用戶端版本指定對應作業，請在 [ **比較**作業] 中，按一下下列其中一項：
    
      - **相同**
    
      - **不相同**
    
      - **新於**
    
      - **新於或相同**
    
      - **舊於**
    
      - **舊於或相同**

6.  若要指定在上述步驟中符合準則時所要執行的動作，請按一下下列其中一個 **動作**：
    
      - 若要允許用戶端登入，請按一下 [ **允許**]。
    
      - 若要允許用戶端登入並接收 Windows Server Update Service 或 Microsoft Update 的更新，請按一下 [ **允許和升級**]。 只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。
        
        <div>
        

        > [!NOTE]  
        > 選取此動作會在使用者下一次登入 Lync 2013 時顯示通知。 通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。 若要避免混淆，您應該僅在更新可用時選擇此動作。

        
        </div>
    
      - 若要允許用戶端登入並顯示從何處下載其他用戶端版本的訊息，請按一下 [以 **URL 允許**]。 您可以在此程式稍後指定 URL。
    
      - 若要防止用戶端登入，請按一下 [ **封鎖**]。
    
      - 若要防止用戶端登入，並允許用戶端從 Windows Server Update Service 或 Microsoft Update 接收更新，請按一下 [ **封鎖和升級**]。 只有在選取 [使用者代理 **OC** ] 時，才可使用此動作。
    
      - 若要防止用戶端登入並顯示要從何處下載其他用戶端版本的訊息，請按一下 [以 **URL 封鎖**]。 您可以在此程式稍後指定 URL。

7.   (選用) 如果您在上一個步驟中按下 [ **允許 url** ] 或 [ **以 url 封鎖** ]，請輸入 **url**中要包含的用戶端下載 URL。

8.  按一下 **[確定]**，然後按一下 [ **認可**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

