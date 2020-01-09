<template>
    <div>
        <el-dialog
                title="提示"
                :visible.sync="dialogVisible"
                width="30%"
                >
            <span>这是一段信息</span>
            <span slot="footer" class="dialog-footer">
                <el-button @click="dialogVisible = false">取 消</el-button>
                <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
            </span>
        </el-dialog>


        <h1>Album Manager</h1>
        <el-form :inline="true" :model="book" class="demo-form-inline">
            <el-form-item label="图书名称">
                <el-input v-model="book.name" placeholder="请输入书名"></el-input>
            </el-form-item>
            <el-form-item label="图书价格">
                <el-input v-model.number="book.price" type="number" placeholder="请输入价格"></el-input>
            </el-form-item>
            <el-form-item>
                <el-button type="primary" @click="addBook">添加图书</el-button>
            </el-form-item>
        </el-form>

        <el-table
                :data="albums"
                style="width: 80%">
            <el-table-column
                    prop="album_id"
                    label="album_id"
                    width="180">
            </el-table-column>
            <el-table-column
                    prop="album_name"
                    label="专辑名称"
                    width="300">
            </el-table-column>
            <el-table-column
                    prop="price"
                    label="专辑价格">
            </el-table-column>
            <el-table-column
                    prop="singers"
                    label="歌手">
            </el-table-column>
            <el-table-column
                    fixed="right"
                    label="操作"
                    width="100">
                <!-- <template slot-scope="album">
                    <el-button @click="deleteBook(book.row)" type="text" size="small">删除</el-button>
                    <el-button @click="dialogVisible=true" type="text" size="small">编辑</el-button>
                </template> -->
            </el-table-column>
        </el-table>
        <!-- <h2>总价格： {{priceTotal}}</h2> -->

    </div>
</template>

<script>
/* eslint-disable */
    // const bookUrl = 'http://127.0.0.1:3000/books'
    export default {
        name: "AlbumManger",
        data(){
            return {
                book:{name:'',price:''},
                dialogVisible:false,
                albums:[{
	"album_id": "3751508",
	"album_name": "A.I. 爱",
	"public_time": "2017-12-11",
	"week": 50,
	"price": 89,
	"cover": "http://imgcache.qq.com/music/photo/album_300/08/300_albumpic_3751508_0.jpg",
	"singers": [{
		"singer_id": "265",
		"singer_name": "王力宏"
    }]},
    ]
            }
        },
        // methods:{
        //     deleteBook(book){
        //         // let index=this.books.findIndex(item=>item.id==book.id)
        //         // this.books.splice(index,1)
        //         fetch(bookUrl, {
        //             body: JSON.stringify(book),
        //             method: 'DELETE',
        //             headers: {
        //             'content-type': 'application/json'
        //             },
        //         })
        //         .then(res => res.json())
        //         .then((books) => {
        //             this.books = books;
        //         })
        //     },
        //     addBook(){
        //         fetch(bookUrl, {
        //             body: JSON.stringify(this.book),
        //             method: 'POST',
        //             headers: {
        //             'content-type': 'application/json'
        //             },
        //         })
        //         .then(res => res.json())
        //         .then((books) => {
        //             this.books = books;
        //         })
        //         // let bk=_.cloneDeep(this.book)
        //         // this.books.push(bk)
        //     }
        // },
        // computed:{
        //     priceTotal(){
        //         return this.books.reduce((prev,book)=>prev+book.price,0)
        //     }
        // },
        created() {
            fetch('/api/all')
            .then(res => res.json())
            .then((albums) => {
                this.albums = albums;
            })
        }
    }
</script>

<style scoped>

</style>