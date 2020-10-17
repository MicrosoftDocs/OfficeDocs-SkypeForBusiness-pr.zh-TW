---
title: Lync Server 2013：測試集區部署
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
ms.openlocfilehash: a808eb575dcccbce45e24f089b41721b41623b13
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519060"
---
# <a name="test-the-pool-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中測試集區部署

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-25_

下列程式說明如何測試前端集區的部署。

<div>

## <a name="to-test-the-pool-deployment"></a>測試集區部署

1.  使用 [Active Directory 電腦和使用者] 將 lync server 2013 部署 (的「系統管理員」角色的 Active Directory 使用者物件，新增至 **CSAdministrator** 群組) 安裝 lync Server 2013 控制台。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您未將適當的使用者和群組新增至 CsAdministors 群組，當您開啟 Lync Server 控制台時，將會收到錯誤訊息，指出「未經授權：存取因角色型存取控制而拒絕 (RBAC) 授權失敗」。

    
    </div>

2.  如果使用者物件目前已登入，請先登出再登入，以註冊新的群組指派。
    
    <div>
    

    > [!NOTE]  
    > 使用者帳戶不可以是執行 Lync Server 2013 之任何伺服器的本機系統管理員。

    
    </div>

3.  使用系統管理帳戶登入安裝 Lync Server 控制台的電腦。

4.  啟動 Lync Server 控制台，然後在出現提示時提供認證。 Lync Server 控制台會顯示部署資訊。

5.  在左導覽列中，按一下 [ **拓撲**]，然後確認服務狀態顯示具有綠色箭號的電腦，且每個已部署並聯機的 Lync server server role 旁都有綠色核取記號的副本狀態。

6.  在左導覽列中，按一下 [ **使用者**]，然後按一下 [ **啟用使用者**]。

7.  在 [ **新增 Lync Server 使用者** ] 頁面上 **，按一下 [新增]**。

8.  若要為您要尋找的物件定義搜尋參數，請在 [ **從 Active Directory 選取** ] 頁面上，選取 [ **搜尋**]，然後選擇性地按一下 [ **新增篩選**]。 您也可以選取 [ **ldap 搜尋** ] 並輸入 ldap 運算式，以篩選或限制將要傳回的物件。 在您決定搜尋選項之後，請 clink **Find**。

9.  在 [搜尋結果] 窗格中，選取此搜尋會話的所有物件，然後按一下 **[確定]**。

10. 在 [ **新增 Lync Server 使用者** ] 頁面上，您所選取的物件會顯示在 [ **使用者** ] 中。 在 [ **指派使用者至集** 區] 清單中，選取物件應該駐留的伺服器。
    
    以下是設定物件的一些選項。
    
      - **產生使用者的 SIP URI**
    
      - **電話**
    
      - **行 URI**
    
      - **會議原則**
    
      - **用戶端版本原則**
    
      - **PIN 原則**
    
      - **外部存取原則**
    
      - **封存原則**
    
      - **位置原則**
    
      - **用戶端原則**
    
    針對測試基本功能的目的，請選取您想要用於 [ **產生使用者的 SIP URI** ] 設定的選項 (設定中的其他選項將使用預設設定) ，然後按一下 [ **啟用**]。

11. 顯示 [摘要] 頁面，在 [ **已啟用** ] 欄中顯示核取記號，表示物件現在可以使用。 [ **SIP 位址** ] 欄會顯示使用者登入設定所需的位址。

12. 將一個使用者登入已加入網域的電腦，並將另一個使用者登入網域中的另一部電腦。

13. 在兩部用戶端電腦上安裝 Lync 2013，然後確認這兩位使用者皆可登入 Lync Server 2013，而且可以相互傳送立即訊息。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

