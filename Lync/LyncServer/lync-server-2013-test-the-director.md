---
title: Lync Server 2013：測試 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad5c885e032800e4233aaa58c5238c066a87a1df
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a>在 Lync Server 2013 中測試 Director

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

在此階段中，您已設定 Director 或 Director 集區，但是您的網域名稱系統 (DNS) SRV 專案仍指向使用集區或 Standard Edition server 來登入的用戶端。 在使用 Director 變更 DNS 記錄以使 Lync 2013 用戶端自動登入之前，請透過手動將用戶端指向 Director 來測試用戶端。

<div>

## <a name="to-test-the-deployment"></a>測試部署

1.  使用屬於**CSAdministrator**群組的網域帳戶，登入已安裝 Lync Server 控制台的電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在功能窗格中，按一下 [**拓撲**]，然後在 [**狀態**] 欄中，確認有箭號 (的綠色伺服器，也就是您 director 或 director 集區的![綠色箭頭) 伺服器圖示](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "具有綠色箭頭的伺服器圖示")。

4.  連接兩部已安裝 Lync Server 2013 用戶端的用戶端電腦，並以 Lync Server 2013 各自啟用的不同使用者帳戶登入每一部電腦。

5.  在其中一部用戶端電腦上，按一下 [**選項**] 功能表，選取 [**個人**設定] 群組，按一下 [**高級**]，按一下 [**手動**設定]，然後將**內部伺服器名稱或 IP 位址**設定為新 Director 或 Director 集區的 FQDN)  (FQDN。

6.  登入這兩個用戶端，並確認使用 Director 登入的用戶端能夠順利登入、查看其他使用者的目前狀態，以及他們是否可以 exchange 立即訊息。

</div>

</div>

<span> </span>

</div>

</div>

</div>

