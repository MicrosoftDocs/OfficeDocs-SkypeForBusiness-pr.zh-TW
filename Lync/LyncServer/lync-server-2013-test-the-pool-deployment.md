---
title: Lync Server 2013： 測試集區部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the pool deployment
ms:assetid: ffd80617-155a-4041-bbeb-74503e7938dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413092(v=OCS.15)
ms:contentKeyID: 48185976
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cded5ae77a7283ba72cbdb73d7472e57b1e8ecf3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141589"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中測試集區部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改主題：** 2013年-09-25_

下列程序說明如何測試部署的前端集區。

<div>

## <a name="to-test-the-pool-deployment"></a>若要測試集區部署

1.  將 Lync Server 2013 部署 （Lync Server 2013 控制台安裝所在） 中系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組使用 Active Directory 電腦和使用者。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您未加入至 CsAdministors 群組新增適當的使用者和群組，您就會收到錯誤，當開啟 Lync Server Control Panel，表示 「 未授權： 存取被拒，因為角色型存取控制 (RBAC) 授權失敗。 」

    
    </div>

2.  如果使用者物件目前登入，請先登出，然後再次登入註冊新的群組指派。
    
    <div>
    

    > [!NOTE]  
    > 使用者帳戶不能執行 Lync Server 2013 的任何伺服器的本機系統管理員。

    
    </div>

3.  使用系統管理帳戶來登入電腦已安裝 Lync Server Control Panel。

4.  啟動 Lync Server 控制台]，並再提供認證，如果系統提示。 Lync Server Control Panel 顯示部署資訊。

5.  在左的導覽列中，[**拓撲**]，然後確認服務狀態顯示帶有綠色箭頭的電腦，且每個已部署且上線的 Lync Server 伺服器角色旁邊為複寫狀態的綠色核取記號。

6.  在左的導覽列中，按一下 [**使用者**]，然後按一下 [**啟用使用者**。

7.  在 [**新增 Lync Server 使用者**] 頁面上，按一下 [**新增**]。

8.  若要定義搜尋參數，針對您想要尋找，請在 [**從 Active Directory 選取**] 頁面的物件您可以選取**搜尋**，然後 （選擇性) 按一下 [**新增篩選**。 您也可以選取 [ **LDAP 搜尋**，然後輸入 LDAP 運算式來篩選或限制將傳回的物件。 **尋找**您已決定搜尋選項之後，嗯。

9.  在 [搜尋結果] 窗格中，針對此搜尋工作階段中，選取所有物件，然後按一下 [**確定]**。

10. 在 [**新增 Lync Server 使用者**] 頁面或多個您所選取的物件是在**使用者**顯示。 在**指派使用者至集區**] 清單中，選取的伺服器應位於物件的位置。
    
    以下是幾個設定物件的選項。
    
      - **產生使用者的 SIP URI**
    
      - **電話語音**
    
      - **線路 URI**
    
      - **會議原則**
    
      - **用戶端版本原則**
    
      - **Pin 碼原則**
    
      - **外部存取原則**
    
      - **封存原則**
    
      - **位置原則**
    
      - **用戶端原則**
    
    用於測試的基本功能的用途，請選取選項您要使用 [**產生使用者的 SIP URI** ] 設定 （在設定其他選項將會使用預設設定），然後按一下 [**啟用**。

11. 摘要] 頁面上，會顯示，指出物件現在已準備好使用**已啟用**] 欄中會顯示一個核取記號。 [ **SIP 位址**] 欄中會顯示您需要的使用者登入設定地址。

12. 一個使用者登入已加入網域的電腦並入另一部電腦的另一位使用者的網域中。

13. 在每個兩部用戶端電腦上安裝 Lync 2013，然後確認 [兩個使用者可以登入 Lync Server 2013，並傳送立即訊息給對方。

</div>

<div>

## <a name="see-also"></a>另請參閱


[部署用戶端和 Lync Server 2013 中的裝置](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

