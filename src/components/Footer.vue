<template>
    <div class="footer">
        <div class="footer-content">
            <div class="footer-menu">
                <ul>
                    title1
                    <li>test001</li>
                    <li>test002</li>
                    <li>test003</li>
                    <li>test004</li>
                    <li>test005</li>
                </ul>
            </div>
            <div class="footer-menu">
                <ul>
                    title2
                    <li>test001</li>
                    <li>test002</li>
                    <li>test003</li>
                    <li>test004</li>
                    <li>test005</li>
                </ul>
            </div>
            <div class="footer-menu">
                <ul>
                    title3
                    <li>test001</li>
                    <li>test002</li>
                    <li>test003</li>
                    <li>test004</li>
                    <li>test005</li>
                </ul>
            </div>
            <div class="footer-menu">
                <ul>
                    title4
                    <li>test001</li>
                    <li>test002</li>
                    <li>test003</li>
                    <li>test004</li>
                    <li>test005</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<style lang="less">
.footer {
    width: 100%;

    .footer-content {
        margin: 0 13.5%;
        min-height: 250px;
        padding: 1rem 1rem 0;
        border-top: 1px solid var(--border-color);
        display: flex;

        .footer-menu {
            flex: 1 0 0;

            ul {
                li {
                    line-height: 2rem;

                    &:nth-child(1) {
                        margin-top: 1.25rem;
                    }
                }
            }
        }
    }
}
</style>