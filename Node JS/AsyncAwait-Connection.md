### AsyncAwait Connect MongoDB

```
const connectDB = async () => {
  try {
    await mongoose.connect('mongodb://localhost/nodeblog_app', {
      useNewUrlParser: true,
      useCreateIndex: true,
      useFindAndModify: false
    });

    console.log('MongoDB Connected...')
  } catch (error) {
    console.error(error.message);

    process.exit(1);
  }
}
```
