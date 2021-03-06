<template>
    <i-article>
        <article>
            <h1>Tag 标签</h1>
            <Anchor title="概述" h2></Anchor>
            <p>对不同维度进行简单的标记和分类。</p>
            <Anchor title="代码示例" h2></Anchor>
            <Demo title="基本用法">
                <div slot="demo">
                    <Tag>标签一</Tag>
                    <Tag>标签二</Tag>
                    <Tag v-if="show" closable @on-close="handleClose">标签三</Tag>
                </div>
                <div slot="desc">
                    <p>简单的展示，添加属性<code>closable</code>可以关闭标签。</p>
                    <blockquote>从 0.9.17 版本开始，点击关闭需使用 @on-close 自己关闭。</blockquote>
                </div>
                <i-code lang="html" slot="code">{{ code.base }}</i-code>
            </Demo>
            <Demo title="样式类型">
                <div slot="demo">
                    <Tag type="border">标签三</Tag>
                    <Tag type="border" closable>标签四</Tag>
                    <Tag type="dot">标签一</Tag>
                    <Tag type="dot" closable>标签二</Tag>
                </div>
                <div slot="desc">
                    <p>通过设置 <code>type</code> 属性为 <code>border</code> 或 <code>dot</code> 来选择不同的样式类型。建议有关闭的某些场景下使用 border，图例的场景下使用 dot。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.type }}</i-code>
            </Demo>
            <Demo title="各种颜色">
                <div slot="demo">
                    <Tag closable color="blue">标签一</Tag>
                    <Tag closable color="green">标签二</Tag>
                    <Tag closable color="red">标签三</Tag>
                    <Tag closable color="yellow">标签四</Tag>
                    <br><br>
                    <Tag type="border" closable color="blue">标签一</Tag>
                    <Tag type="border" closable color="green">标签二</Tag>
                    <Tag type="border" closable color="red">标签三</Tag>
                    <Tag type="border" closable color="yellow">标签四</Tag>
                    <br><br>
                    <Tag type="dot" closable color="blue">标签一</Tag>
                    <Tag type="dot" closable color="green">标签二</Tag>
                    <Tag type="dot" closable color="red">标签三</Tag>
                    <Tag type="dot" closable color="yellow">标签四</Tag>
                </div>
                <div slot="desc">
                    <p>四种不同的颜色。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.color }}</i-code>
            </Demo>
            <Demo title="动态添加和删除">
                <div slot="demo">
                    <Tag v-for="item in count" closable>标签{{ item + 1 }}</Tag>
                    <i-button icon="ios-plus-empty" type="dashed" size="small" @click="count += 1">添加标签</i-button>
                </div>
                <div slot="desc">
                    <p>用数组生成一组标签，可以动态添加和删除。</p>
                </div>
                <i-code lang="html" slot="code">{{ code.add }}</i-code>
            </Demo>
            <div class="api">
                <Anchor title="API" h2></Anchor>
                <Anchor title="Tag props" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>属性</th>
                            <th>说明</th>
                            <th>类型</th>
                            <th>默认值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>closable</td>
                            <td>标签是否可以关闭</td>
                            <td>Boolean</td>
                            <td>false</td>
                        </tr>
                        <tr>
                            <td>type</td>
                            <td>标签的样式类型，可选值为 <code>border</code>、<code>dot</code>或不填</td>
                            <td>String</td>
                            <td>-</td>
                        </tr>
                        <tr>
                            <td>color</td>
                            <td>标签颜色，可选值为<code>blue</code>、<code>green</code>、<code>red</code>、<code>yellow</code></td>
                            <td>String</td>
                            <td>-</td>
                        </tr>
                    </tbody>
                </table>
                <Anchor title="Tag events" h3></Anchor>
                <table>
                    <thead>
                        <tr>
                            <th>事件名</th>
                            <th>说明</th>
                            <th>返回值</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>on-close</td>
                            <td>关闭时触发</td>
                            <td>event</td>
                        </tr>
                    </tbody>
                </table>
            </div>
        </article>
    </i-article>
</template>
<script>
    import iArticle from '../../components/article.vue';
    import iCode from 'iCode';
    import Demo from '../../components/demo.vue';
    import Code from '../../code/tag';
    import Anchor from '../../components/anchor.vue';

    export default {
        components: {
            iArticle,
            iCode,
            Demo,
            Anchor
        },
        data () {
            return {
                code: Code,
                count: 3,
                show: true
            }
        },
        methods: {
            handleClose () {
                this.show = false;
            }
        }
    }
</script>