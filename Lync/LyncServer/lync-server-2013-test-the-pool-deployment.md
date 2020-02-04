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
ms.openlocfilehash: cfde95e7323d68f05e78f670a6b027a5949f0169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-pool-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中測試集區部署

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-09-25_

下列程式說明如何測試前端池的部署。

<div>

## <a name="to-test-the-pool-deployment"></a>測試池部署

1.  使用 Active Directory 電腦和使用者將 Lync Server 2013 部署（安裝 Lync Server 2013 控制台）的系統管理員角色的 Active Directory 使用者物件新增至**CSAdministrator**群組。
    
    <div>
    

    > [!IMPORTANT]  
    > 如果您沒有將適當的使用者和群組新增至 CsAdministors 群組，當您開啟 Lync Server 控制台時，會收到錯誤訊息，指出「未授權：存取權因角色式存取控制（RBAC）授權失敗」。

    
    </div>

2.  如果使用者物件目前已登入，請先登出後再登入，以註冊新的群組指派。
    
    <div>
    

    > [!NOTE]  
    > 使用者帳戶不能是任何執行 Lync Server 2013 的伺服器的本機系統管理員。

    
    </div>

3.  使用 [系統管理] 帳戶登入安裝 Lync Server [控制台] 的電腦。

4.  啟動 Lync Server [控制台]，然後在出現提示時提供認證。 Lync Server [控制台] 會顯示部署資訊。

5.  在左側導覽列中，按一下 [**拓撲**]，然後確認 [服務狀態] 會以綠色箭號顯示電腦，且已部署並線上的每個 Lync server 伺服器角色旁邊都會出現綠色的核取記號。

6.  在左側導覽列中，按一下 [**使用者**]，然後按一下 [**啟用使用者**]。

7.  在 [**新的 Lync Server 使用者**] 頁面上 **，按一下 [新增]**。

8.  若要定義您想要尋找之物件的搜尋參數，您可以在 [**從 Active Directory 中選取**] 頁面上選取 [**搜尋**]，然後按一下 [**新增篩選**] （選擇性）。 您也可以選取 [ **ldap 搜尋**]，然後輸入 ldap 運算式來篩選或限制將傳回的物件。 在您決定搜尋選項之後，請 clink [**尋找**]。

9.  在 [搜尋結果] 窗格中，選取此搜尋會話的所有物件，然後按一下 **[確定]**。

10. 在 [**新的 Lync Server 使用者**] 頁面上，您所選取的物件就會顯示在 [**使用者**] 顯示幕中。 在 [**指派使用者至池中**] 清單中，選取物件應駐留在其中的伺服器。
    
    以下是一些設定物件的選項。
    
      - **產生使用者的 SIP URI**
    
      - **$**
    
      - **行 URI**
    
      - **會議原則**
    
      - **用戶端版本原則**
    
      - **PIN 原則**
    
      - **外部存取原則**
    
      - **存檔原則**
    
      - **位置原則**
    
      - **用戶端原則**
    
    針對測試基本功能的目的，請針對**產生使用者的 SIP URI**設定選取您想要的選項（[設定] 中的其他選項將使用預設設定），然後按一下 [**啟用**]。

11. 隨即會顯示 [摘要] 頁面，其中顯示 [**啟用**] 欄中的核取記號，表示現在已準備好使用這些物件。 [ **SIP 位址**] 欄會顯示使用者登入設定所需的位址。

12. 在已加入網域的電腦上登入一個使用者，而另一個使用者則在網域中的另一部電腦上。

13. 在兩個用戶端電腦上安裝 Lync 2013，然後確認這兩個使用者都可以登入 Lync Server 2013，而且可以傳送立即訊息給對方。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中部署用戶端和裝置](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

