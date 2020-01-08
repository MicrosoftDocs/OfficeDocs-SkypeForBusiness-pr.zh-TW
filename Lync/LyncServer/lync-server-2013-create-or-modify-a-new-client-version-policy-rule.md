---
title: Lync Server 2013：建立或修改新的用戶端版本原則規則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a new client version policy rule
ms:assetid: 6f879d99-8401-41e0-a562-195c890d63ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898478(v=OCS.15)
ms:contentKeyID: 50873758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa5f9074f928a9bec20ca275487806b790a0226b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-rule-in-lync-server-2013"></a>在 Lync Server 2013 中建立或修改新的用戶端版本原則規則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-21_

用戶端版本原則規則定義使用者嘗試使用特定用戶端和用戶端版本登入時應採取的動作。 您可以從 Lync Server 2013 [控制台] 建立或修改用戶端版本原則的個別規則。

<div>


> [!IMPORTANT]  
> 規則會依優先順序順序列出。 例如，如果您有允許執行版本1.5 的用戶端連線的規則，接著是一個規則，該規則會封鎖執行版本低於2.0 之版本的用戶端，且會允許執行版本1.5 的用戶端連線。



</div>

<div>

## <a name="to-create-or-modify-client-version-policy-rules-with-lync-server-control-panel"></a>使用 Lync Server [控制台] 建立或修改用戶端版本原則規則

1.  使用 Lync Server [控制台][在 Lync server 2013 中建立或修改新的用戶端版本原則](lync-server-2013-create-or-modify-a-new-client-version-policy.md)。

2.  在 [**編輯用戶端版本原則**] 頁面上，執行下列其中一項操作：
    
      - 按一下 [**新增**]，建立新的用戶端版本規則。
    
      - 在清單中按一下其中一個已定義的用戶端類型，然後按一下 [**顯示詳細資料**]。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用萬用字元來指示用戶端類型。

    
    </div>

3.  在 [**使用者代理**] 中，選取用戶端類型。

4.  在 [**版本號碼**] 底下，執行下列動作：
    
      - 在 [**主要版本**] 中，輸入與用戶端主要版本相對應的數位。
    
      - 在 [**次要版本**] 中，輸入與用戶端次要發行版本相對應的數位。
    
      - 在 [**組建**] 中，輸入與用戶端主要和次要版本相對應的數位。
    
      - 在 [Update] （**更新**）中，輸入與用戶端更新版本相對應的數位。
    
    <div>
    

    > [!NOTE]  
    > 您可以使用萬用字元來表示用戶端的版本號碼。

    
    </div>

5.  若要針對您在上述步驟中指定的用戶端版本指定相符的作業，請在 [**比較**] 作業中，按一下下列其中一個選項：
    
      - **相同**
    
      - **不相同**
    
      - **新於**
    
      - **新於或相同**
    
      - **舊於**
    
      - **舊於或相同**

6.  若要指定在滿足上述步驟中的準則時要執行的動作，請按一下下列其中一個**動作**：
    
      - 若要允許用戶端登入，請按一下 [**允許**]。
    
      - 若要允許用戶端登入並從 Windows Server Update Services 或 Microsoft Update 接收更新，請按一下 [**允許及升級**]。 只有在選取 [使用者代理**OC** ] 時，才能使用此動作。
        
        <div>
        

        > [!NOTE]  
        > 選取此動作會在使用者下次登入 Lync 2013 時，顯示通知。 通知指出有可用的更新，即使更新還沒有發佈至 Windows Server Update Service 或 Microsoft Update。 為避免混淆，您應該僅在有可用更新時選擇此動作。

        
        </div>
    
      - 若要允許用戶端登入，並顯示有關下載其他用戶端版本之位置的訊息，請按一下 [**允許使用 URL**]。 您可以稍後在此程式中指定 URL。
    
      - 若要防止用戶端登入，請按一下 [**封鎖**]。
    
      - 若要防止用戶端登入，並允許用戶端從 Windows Server Update Services 或 Microsoft Update 接收更新，請按一下 [**封鎖及升級**]。 只有在選取 [使用者代理**OC** ] 時，才能使用此動作。
    
      - 若要防止用戶端登入，並顯示一則訊息，瞭解如何下載另一個用戶端版本，請按一下 [**以 URL 封鎖**]。 您可以稍後在此程式中指定 URL。

7.  可選如果您在上一個步驟中按一下 [**允許 url**或**包含 url 的封鎖**]，請輸入用戶端下載 Url，以加入**url**中的郵件。

8.  按一下 **[確定]**，然後按一下 [**確認**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

